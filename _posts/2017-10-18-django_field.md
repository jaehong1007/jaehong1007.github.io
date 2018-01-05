## DJango Field

### One-to-one Relationship

Usermode 

- username
- password

User info model

- name
- Phone number



user.userinfo.name



###Foreign Key(Many-to-One)

School (여기에는 student라는 데이터가 저장되지 않음)

Student(Many가 되는 쪽에 Foreign키를 지정)(School의 pk가 저장됨)

```
Class Students():
	school = models.Foreignkey(school)
```

AAA.school =school의pk

A.student = student의 pk



## Many-to-Many

Group

Student

중간모델이 자동으로 만들어짐

> Group.member()

through = '중간자 모델'

> Post.users.all() - 라이크를 한 모든 사람



Related_name = 'like_posts'(역참조)

> User.like_posts.all() - like한 모든 사람

> post.like_users.all() - 