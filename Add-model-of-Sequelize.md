// [Your project]/models/post.js // sequelize models
```javascript
module.exports = function(sequelize, DataTypes) {
    const Post = sequelize.define('Post', {
        title: DataTypes.STRING,
        content: DataTypes.STRING
    });

    Post.associate = function(models) {
        Post.belongsTo(models.User);
    };

    return Post;
};
```

#### Create Model AI
// [Your project]/admin-interface/models/Post.js
```javascript
const { ModelAbstract } = require('admin-interface');
const { Post } = require('../../models'); // sequelize models

class PostAI extends ModelAbstract {
    getModel() {
        return Post;
    }
}

module.exports = PostAI;
```
#### Connect Model AI to Admin Interface

// [Your project]/admin-interface.yaml
```yml
Model:
    Post: ./admin-interface/models/Post.js
```