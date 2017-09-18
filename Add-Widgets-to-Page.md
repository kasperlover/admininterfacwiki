#### Get WidgetFactory
```javascript
const { WidgetFactory } = require('admin-interface');
```

#### Set widgets
```javascript
// [Your project]/admin-interface/pages/MainPage.js
const { PageAbstract, WidgetFactory } = require('admin-interface');

class MainPage extends PageAbstract {
    
    getUrl() {
        return '/';
    }

    getWidgets() {
        return [
            WidgetFactory('ModelsInfoWidget')
                .setOptions({
                    models: [
                        { model: 'Post', icon: 'note', color: 'pink' }
                    ]
                })
        ];
    }

    render(req, res) {
        return res.render('pages/main', {
            $page: this
        });
    }

}

module.exports = MainPage;
```