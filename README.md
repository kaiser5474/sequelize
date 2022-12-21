# sequelize

```javascript
Post.findAll({
attributes: {
  include: [
  [
  // Note the wrapping parentheses in the call below!
  sequelize.literal(`(SELECT COUNT(*) FROM reactions AS reaction WHERE reaction.postId = post.id AND reaction.type = "Laugh" )`), 'laughReactionsCount'
]
]
}
});
```

### For select column with as in attributes

spanish is the name of the column in database and values is the new name
this is like
Select id, spanish as values, tag from ...
attributes: ["id", ["spanish", "value"], "tag"],

### For change name primary key

id:
{
type: DataTypes.INTEGER,
primaryKey: true, //this is for creater primary key
autoIncrement: true,
},
