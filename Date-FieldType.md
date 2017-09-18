#### Default options:
* format: `YYYY-MM-DD hh:mm:ss`
* time: `true`
* date: `true`

#### Using
```javascript
new FieldFactory('CreatedAt', 'Date').setTitle('Created At').setOptions({
    format: 'YYYY-MM-DD',
    time: false
})
```