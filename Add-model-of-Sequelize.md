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