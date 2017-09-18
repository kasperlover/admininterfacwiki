// [Your project]/admin-interface/models/User.js
```javascript
const { ModelAbstract } = require('admin-interface');
const { User } = require('../../models'); // sequelize models

class UserAI extends ModelAbstract {
    getModel() {
        return User;
    }

    getReferencesStrategy() {
        return ['Post']; // Key models from yaml config
    }
}

module.exports = UserAI;
```