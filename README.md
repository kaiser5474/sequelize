# Sequelize

## Inyect consult

```javascript
Post.findAll({
attributes: {
  include: [
    [
    // Note the wrapping parentheses in the call below!
    sequelize.literal(`(SELECT COUNT(*) FROM reactions WHERE reaction.postId = post.id AND reaction.type = "Laugh" )`), 'laughReactionsCount'
    ]
  ]
}
});
```

### For select column with as in attributes

spanish is the name of the column in database and values is the new name
this is like
Select id, spanish as values, tag from ...

```javascript
attributes: ["id", ["spanish", "value"], "tag"],
```

### For change name primary key

```javascript
id: {
  type: DataTypes.INTEGER,
  primaryKey: true, //this is for creater primary key
  autoIncrement: true,
},
```
## Allow Null

Allow null for defaul is true, for change

```javascript
user_name: {
  type: DataTypes.STRING(100), 
  allowNull: false, //we need to do this
},
```
