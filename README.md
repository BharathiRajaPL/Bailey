# Bailey



# 1)Write a multiplication function in javascript to use like this.

function mul(x) {
return function (y) {
return function (z) {
return x*y*z;
}
}
}
console.log(mul(2)(3)(4));

# 2)Which of the following code snippet append an element value at the end of the array, arr?

a) arr[arr.length+1] = value

# b) arr[arr.length] = value===> Correct Answer

c) arr[arr.length - 1] = value

d) arr = arr + value 

# 3) JavaScript: what is the correct way to create a JavaScript array?

# a) var items = ["Orange", "Apple"]; ===> Correct Answer

b) var items = {"Orange", "Apple"};

c) var items = new array("Orange", "Apple");

d) var items[] = {"Orange", "Apple"};

# 4)JavaScript: What is the output of the following code
foo = 1;

(function() {

   foo = 2;

})();

var x = function () {

  foo = 3;

};

(function() {

   var foo = 4;

})();

# console.log(foo); // Result : 2

# 5) React countdown timer

class Clock extends React.Component {
  format(time) {
    let seconds = time % 60;
    let minutes = Math.floor(time / 60);
    minutes = minutes.toString().length === 1 ? "0" + minutes : minutes;
    seconds = seconds.toString().length === 1 ? "0" + seconds : seconds;
    return minutes + ':' + seconds;
  }
  render () {
    const {time} = this.props;
    return (
      <div className="displayedTime">
        <h1>{this.format(time)}</h1>
      </div>
    )
  }
}

class Input extends React.Component {
  
  onSubmit(event) {
    event.preventDefault();
    const strSeconds = this.refs.seconds.value;
    if(strSeconds.match(/[0-9]/)) {
      this.refs.seconds.value = '';
      this.props.onSetCountdown(parseInt(strSeconds, 10));
    }
  }
  
  render() {
    return (
      <form ref="form" onSubmit={this.onSubmit.bind(this)}>
        <input type="text" ref="seconds" placeholder="enter time in seconds"/>
        <input type="submit" value="Start"></input>
      </form>
    )
  }
}

class Button extends React.Component {
  render() {
    return (
        <button onClick={this.props.onClickHandler}>{this.props.label}</button>    
    );
  }
}

class App extends React.Component {
  constructor(props) {
    super(props);
    this.state = {
      count: 0,
      running: false,
    }
  }
  
  componentDidUpdate(prevProps, prevState) {
    if(this.state.running !== prevState.running){
      switch(this.state.running) {
        case true:
          this.handleStart();
      }
    }
  }
  
  handleStart() {
    this.timer = setInterval(() => {
      const newCount = this.state.count - 1;
      this.setState(
        {count: newCount >= 0 ? newCount : 0}
      );
    }, 1000);
  }
  
  handleStop() {
    if(this.timer) {
      clearInterval(this.timer);
      this.setState(
        {running:false}
      );
    }
  }
  
  handleReset() {
    this.setState(
      {count: 0}
    );
  }
  
  handleCountdown(seconds) {
    this.setState({
      count: seconds,
      running: true
    })
  }
  
  render() {
    const {count} = this.state;
    return (
      <div className="container">
        <Clock time={count}/>
        <Input onSetCountdown={this.handleCountdown.bind(this)}/>
        <Button label="stop" onClickHandler={this.handleStop.bind(this)}/>
        <Button label="reset" onClickHandler={this.handleReset.bind(this)}/>
      </div>
    )
  }
}

ReactDOM.render(<App/>, document.getElementById('app'));
