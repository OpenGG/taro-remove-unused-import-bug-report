# taro-remove-unused-import-bug-report

## Reproduce

### install

```bash
npm install @tarojs/cli -g

git clone https://github.com/OpenGG/taro-remove-unused-import-bug-report.git

cd taro-remove-unused-import-bug-report/
npm install
```

### build

```bash
npm run build:h5
```

## problem

There is undefined variable GOOGLE and BAIDU in `dist/js/app.js`

## cause

[babel-plugin-danger-remove-unused-import](https://github.com/imcuttle/babel-plugin-danger-remove-unused-import) doesn't handle computed object property well.

See: https://github.com/imcuttle/babel-plugin-danger-remove-unused-import/pull/3

## suggested solution

Make `babel-plugin-danger-remove-unused-import` optional.
