# 씨퀄라이즈 설정

1. 모듈 설치 
```jsx
npm i sequelize mysql2 -S
npm i sequelize-cli -D
```
2. 씨퀄라이즈 사용 준비
```jsx
npx sequelize init
```
3. config/config.json 파일 수정
```jsx
{
  "development": {
    "username": "root",
    "password": "원하는 비밀번호",
    "database": "database_development", //원하는 db 이름 변경 
    "host": "127.0.0.1",
    "dialect": "mysql"
  },
  "test": {
    "username": "root",
    "password": null,
    "database": "database_test",
    "host": "127.0.0.1",
    "dialect": "mysql"
  },
  "production": {
    "username": "root",
    "password": null,
    "database": "database_production",
    "host": "127.0.0.1",
    "dialect": "mysql"
  }
}
```
4. 데이터 베이스 생성하기 
npx sequelize db:create

5. 데이터 베이스 생성후, workbench 로 확인 하기!(데이터베이스 잘 생성 되었나)

6. 테이블 생성(회원가입)

npx sequelize model:generate --name User --attributes //email:string,nickname:string,password:string// 부분 변경 가능

7. models 폴더에 users.js 생기고, migration 폴더에 숫자-create-user.js 같은 이름으로 파일 하나 생성 됨.

8. models/users.js 파일 수정
```jsx
'use strict';
const {
  Model
} = require('sequelize');
module.exports = (sequelize, DataTypes) => {
  class User extends Model {
    /**
     * Helper method for defining associations.
     * This method is not a part of Sequelize lifecycle.
     * The `models/index` file will call this method automatically.
     */
    static associate(models) {
      // define association here
    }
  };
  User.init({
    userId: { // userId를 따로, 설정 해줌 (이 부분이 변경 됨)
      primaryKey: true,
      type: DataTypes.INTEGER,
    },
    email: DataTypes.STRING,
    nickname: DataTypes.STRING,
    password: DataTypes.STRING
  }, {
    sequelize,
    modelName: 'User',
  });
  return User;
};
```

9. migration/숫자 -create -user.js 파일 수정
```jsx
'use strict';
const {
  Model
} = require('sequelize');
module.exports = (sequelize, DataTypes) => {
  class User extends Model {
    /**
     * Helper method for defining associations.
     * This method is not a part of Sequelize lifecycle.
     * The `models/index` file will call this method automatically.
     */
    static associate(models) {
      // define association here
    }
  };
  User.init({
    userId: { //id를 userId 로 바꿔줌 
      primaryKey: true,
      type: DataTypes.INTEGER,
    },
    email: DataTypes.STRING,
    nickname: DataTypes.STRING,
    password: DataTypes.STRING
  }, {
    sequelize,
    modelName: 'User',
  });
  return User;
};
```

10. 테이블 생성하기 
```jsx
npx sequelize db:migrate
```

```jsx
Sequelize CLI [Node: 15.5.1, CLI: 6.2.0, ORM: 6.4.0]

Loaded configuration file "config/config.json".
Using environment "development".
== 20210214073234-create-user: migrating =======
== 20210214073234-create-user: migrated (0.031s)
```
이렇게 메세지가 뜬다면 성공!

[공식문서](https://sequelize.org/main/manual/migrations.html)
[참고](https://github.com/sequelize/cli)
[출처](https://spartacodingclub.kr/online/node_plus)