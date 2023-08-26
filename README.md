# Use Functions to render data at the right time

```jsx
/**
 * ---------------------------------------------------------
 * USE FUNCTIONS TO DISPLAY THE RIGHT DATA AT THE RIGHT TIME
 * ---------------------------------------------------------
 */

import "./App.css";

const tahoePeaks = [
  { name: "Freel", elevation: 10891 },
  { name: "Monument", elevation: 10067 },
  { name: "Pyramid", elevation: 9983 },
  { name: "Tallac", elevation: 9735 },
];
// a function that will take in few properties
function List({ data, renderItem, renderEmpty }) {
  // if data does not exist then return renderEmpty function otherwise
  return !data.length ? (
    renderEmpty
  ) : (
    //
    <ul>
      {data.map((item) => (
        <li key={item.name}>{renderItem(item)}</li>
      ))}
    </ul>
  );
}

function App() {
  return (
    <div>
      <h1>Use functions to display data at the right time</h1>
      <List
        data={tahoePeaks}
        renderEmpty={<p>This is Empty</p>}
        renderItem={(item) => (
          <>
            {item.name} - {item.elevation} ft.
          </>
        )}
      />
    </div>
  );
}

export default App;
```
