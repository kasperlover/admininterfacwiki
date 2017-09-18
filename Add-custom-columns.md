#### Get Column
```javascript
const { Column } = require('admin-interface');
```

#### Set Columns Strategy
```javascript
const { ModelAbstract, Column } = require('admin-interface');
const { Post, User } = require('../../models'); // sequelize models

class PostAI extends ModelAbstract {
    getModel() {
        return Post;
    }

    getColumnsStrategy() {
        return [
            new Column().setTitle('Post ID').setField('id'),
            new Column().setTitle('Title').setField('title'),
            new Column().setName('User login').setReferenceAndKey('login', 'User'),
            new Column().setTitle('Async data').setValue(async (item) => {
                const { email } = await User.findById(item.UserId);
                return `Author Email: ${ email }`;
            }),
            new Column().setTitle('Static value').setValue('It is static data')
        ];
    }
}

module.exports = PostAI;

```