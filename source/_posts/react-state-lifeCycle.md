---
title: react_state&lifeCycle
date: 2017-08-21 20:04:37
tags: [JavaScript,React]
category: JavaScript 
---
在学习React——State和生命周期时，觉得这个组件Demo比较全面，故做个记录，方便之后查找。
<!-- more -->
```
class Clock extends React.Component{
  constructor(props){
    super(props);
    this.state={date:new Date()};
  }
 componentDidMount() {
    this.timerID = setInterval(
      () => this.tick(),
      1000
    );
  }

  componentWillUnmount() {
    clearInterval(this.timerID);
  }

  tick() {
    this.setState({
      date: new Date()
    });
  }
  render(){
    return (
    <div>
        <h1>Hello!</h1>
        <h2>It's {this.state.date.toLocaleTimeString()}.</h2>
    </div>
    );
  }
}

ReactDOM.render(
  <Clock />,
  document.getElementById('root')
);
```
