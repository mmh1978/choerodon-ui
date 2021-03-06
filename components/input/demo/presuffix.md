---
order: 8
title:
    zh-CN: 前缀和后缀
    en-US: prefix and suffix
---

## zh-CN

在输入框上添加前缀或后缀图标。

## en-US

Add prefix or suffix icons inside input.

````jsx
import { Input, Icon } from 'choerodon-ui';

class App extends React.Component {
  constructor(props) {
    super(props);
    this.state = {
      userName: 'xxx',
    };
  }

  emitEmpty = () => {
    this.userNameInput.focus();
    this.setState({ userName: '' });
  }

  onChangeUserName = (e) => {
    this.setState({ userName: e.target.value });
  }

  render() {
    const { userName } = this.state;
    const suffix = userName ? <Icon type="close" onClick={this.emitEmpty} /> : null;
    return (
      <Input
        placeholder="Enter your username"
        prefix="input-"
        suffix={suffix}
        label="username"
        value={userName}
        onChange={this.onChangeUserName}
        ref={node => this.userNameInput = node}
        copy
      />
    );
  }
}

ReactDOM.render(<App />, mountNode);
````

````css
.anticon-close-circle {
  cursor: pointer;
  color: #ccc;
  transition: color 0.3s;
  font-size: 12px;
}
.anticon-close-circle:hover {
  color: #999;
}
.anticon-close-circle:active {
  color: #666;
}
````
