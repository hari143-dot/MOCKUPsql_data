2.1 SELECT DISTINCT email_domain
FROM users
WHERE email_domain LIKE '%.edu'
LIMIT 25;

2.2 SELECT city, COUNT (*) FROM users
WHERE city = 'New York'
AND email_domain LIKE '%.edu';

2.3 SELECT COUNT (*) AS 'Mobile App Users' FROM users
WHERE mobile_app IS NOT NULL;

3. SELECT sign_up_at, strftime ('%H', sign_up_at) AS 'Hour',
COUNT (*) AS 'Users Signed Up'
FROM users
GROUP BY 2
ORDER BY 3 DESC;

4.1 SELECT u.email_domain, p.learn_cpp, p.learn_sql, p.learn_html, p.learn_javascript, p.learn_java
FROM users u
LEFT JOIN progress p
ON u.user_id = p.user_id
GROUP BY 1
ORDER BY 1
LIMIT 10;

4.2 SELECT users.user_id, users.city, progress.learn_cpp, progress.learn_html, progress.learn_java, progress.learn_javascript, progress.learn_sql
FROM users
LEFT JOIN progress
ON users.user_id = progress.user_id
WHERE city ='New York'
LIMIT 25;

4.3 SELECT users.user_id, users.city, progress.learn_cpp, progress.learn_html, progress.learn_java, progress.learn_javascript, progress.learn_sql
FROM users
LEFT JOIN progress
ON users.user_id = progress.user_id
WHERE city ='Chicago'
LIMIT 25;
