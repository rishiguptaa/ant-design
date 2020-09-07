---
order: 3.1
title:
  zh-CN: 必选样式
  en-US: Required style
---

## zh-CN

通过 `requiredMark` 切换必选与可选样式。

## en-US

Switch required or optional style with `requiredMark`.

```tsx
import React, { useState } from 'react';
import { Form, Input, Button, Radio } from 'antd';

const FormLayoutDemo = () => {
  const [form] = Form.useForm();
  const [requiredMark, setRequiredMarkType] = useState<boolean | 'optional'>('optional');

  const onRequiredTypeChange = ({ requiredMark }) => {
    setRequiredMarkType(requiredMark);
  };

  return (
    <Form
      form={form}
      layout="vertical"
      initialValues={{ requiredMark }}
      onValuesChange={onRequiredTypeChange}
      requiredMark={requiredMark}
    >
      <Form.Item label="Required Mark" name="requiredMark">
      </Form.Item>
      <Form.Item label="Field A" required>
        <Input placeholder="input placeholder" />
      </Form.Item>
      <Form.Item>
        <Button type="primary">Submit</Button>
      </Form.Item>
    </Form>
  );
};

ReactDOM.render(<FormLayoutDemo />, mountNode);
```
