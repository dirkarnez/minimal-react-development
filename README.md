[minimal-react-development](https://dirkarnez.github.io/minimal-react-development)
==================================================================================
Not for production

### Lazy-load
```jsx
var ReactGridLayoutLibrary = null;

function MyGrid() {
  const [ loaded, setLoaded ] = React.useState(false);

  React.useEffect(() => {
    fetch("./ReactGridLayoutLibrary.v.2.1.1.js")
    .then(a => a.text())
    .then(a => {
        eval(a);
        ReactGridLayoutLibrary.ReactGridLayout.WidthProvider(ReactGridLayoutLibrary.ReactGridLayout);
        setLoaded(true);
    });

  }, []);
	return (
    loaded && <MyGridReal/>
	);
}
```
