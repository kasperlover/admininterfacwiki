#### Get PageAbstract
```javascript
const PageAbstract = require('admin-interface').PageAbstract;
```

#### Create page class
```javascript
// [Your project]/admin-interface/pages/Demo.js
const PageAbstract = require('admin-interface').PageAbstract;

class DemoPage extends PageAbstract {
    
    getUrl() {
        return '/demo';
    }

    render(req, res) {
        return res.render('pages/demo');
    }

}

module.exports = DemoPage;
```