#### Get FieldFactory
```javascript
const { FieldFactory } = require('admin-interface');
```

#### Set Fields Strategy
```javascript
FieldFactory( "model field name", "FieldType key" )
```
// [Your project]/admin-interface/models/Post.js
```javascript
const { ModelAbstract, FieldFactory } = require('admin-interface');
const { Post } = require('../../models'); // sequelize models

class PostAI extends ModelAbstract {
    getModel() {
        return Post;
    }

    getFieldsStrategy() {
        return [
            new FieldFactory('title', 'String').setTitle('Title'),
            new FieldFactory('content', 'String').setTitle('Content'),
            new FieldFactory('UserId', 'Reference').setTitle('Author').setOptions({
                label: 'login'
            }),
            new FieldFactory('CreatedAt', 'Date').setTitle('Created At').setDisable(true),
            new FieldFactory('UpdatedAt', 'Date').setTitle('Updated At').setDisable(true),
        ];
    }
}

module.exports = PostAI;
```