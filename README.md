# validate
纯javascript基于数据的表单验证

## 使用说明

```js
import { va } from '../utils/validate'

constructor() {
  super(...arguments)
  this.state = {
    formData: {
      name: '',
      idcard: '',
      type: '',
      phone: '15888867998'
    },
    rule: [
      {
        key: 'name',
        required: true,
        message: '姓名'
      },
      {
        key: 'idcard',
        required: true,
        message: '身份证号码',
        type: 'idcard'
      }
    ]
  }

formSubmit() {
  const { name, idcard } = this.state.formData
  // 单个效验
  if (!va({ name: name}, this.state.rule[0]).includes(false)) {}
  
  // 多个效验
  if (!va(this.state.formData, this.state.rule).includes(false)) {}
  
}
```
