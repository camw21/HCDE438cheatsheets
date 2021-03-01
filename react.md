# react

### Componenets

```jsx
// "custom" HTML element
function Component(props){
    const [text, setText] = useState('')
    return <input classnMae="text-input">
        value={text}
        onChange={e=> setText(e.target.value)}
}
```

Then you can use it like this:
```jsx
// the text color of the <input /> inside the Component
// will be red
function App(){
    return <Compoent color="red">
}
```
### props

props can be anything at all
```jsx
// variable prop
// this is for passing data DOWN into a child component
<Component color="green">
```

```jsx
// function prop
// for passing data UP from child to parent
<Component onChange={e=> console.log(e)}>
```

Props act just like state in a componenet. If a 
prop changes its value, it will re-render the componenet, just like if state changes.

If you need to share "state between componenets, 
then you should create your "state" variable in
a common Parent componenet.

```jsx
function SettingsMenu(){
        const [username, setUsername] = useState('')
        return <section>
            <NamePicker setUsername={setUsername} username={username}>
            <UserProfile username={username}>
        </section>
}
```

In the aboce example, the NamePicker and the user propfile don't manage the
username "state"... instaead, the "username" is managed in their shared Parent (SettingsMenu)