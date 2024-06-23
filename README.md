# Description

This is a Demo to showcase about using React and MUI in pure HTML and Vanilla JS.

# Considerations

-   As this approach download the entire React and MUI library code to the client browser, the performance will be affected.

# Scripts

## Scripts for React

```HTML
    <!-- React -->
    <script
        src="https://unpkg.com/react@18/umd/react.development.js"
        crossorigin="anonymous"
    ></script>
    <script src="https://unpkg.com/react-dom@18/umd/react-dom.development.js"></script>
```

## Scripts for MUI

```HTML
    <!-- MUI -->
    <script
        src="https://unpkg.com/@mui/material@5.15.20/umd/material-ui.development.js"
        crossorigin="anonymous"
    ></script>
    <script
        src="https://unpkg.com/@babel/standalone@latest/babel.min.js"
        crossorigin="anonymous"
    ></script>

    <!-- Fonts to support Material Design -->
    <link
        rel="preconnect"
        href="https://fonts.googleapis.com"
    />
    <link
        rel="preconnect"
        href="https://fonts.gstatic.com"
        crossorigin
    />
    <link
        rel="stylesheet"
        href="https://fonts.googleapis.com/css2?family=Roboto:wght@300;400;500;700&display=swap"
    />

    <!-- Icons to support Material Design -->
    <link
        rel="stylesheet"
        href="https://fonts.googleapis.com/icon?family=Material+Icons"
    />
```

## Example of Usage

```JavaScript
const { useState } = React;

const {
    colors,
    CssBaseline,
    ThemeProvider,
    createTheme,
    Box,
    FormControl,
    InputLabel,
    Select,
    MenuItem,
} = MaterialUI;

const theme = createTheme({
    palette: {
        primary: {
            main: '#556cd6',
        },
        secondary: {
            main: '#19857b',
        },
        error: {
            main: colors.red.A400,
        },
    },
});

const App = () => {
    const [age, setAge] = useState(null);

    const onClickHandler = () => {
        alert('hi');
    };

    const selectOnChangeHandler = (e) => {
        const value = e.target.value;
        setAge(value);
    };

    return (
        <Box
            width={500}
            margin={1}
        >
            <FormControl>
                <InputLabel id='demo-simple-select-label'>
                    Age
                </InputLabel>
                <Select
                    labelId='demo-simple-select-label'
                    id='demo-simple-select'
                    value={age ?? 0}
                    label='Age'
                    onChange={selectOnChangeHandler}
                >
                    <MenuItem
                        value={0}
                        disabled
                    >
                        -
                    </MenuItem>
                    <MenuItem value={10}>Ten</MenuItem>
                    <MenuItem value={20}>Twenty</MenuItem>
                    <MenuItem value={30}>Thirty</MenuItem>
                </Select>
            </FormControl>

            <Button
                onClick={onClickHandler}
                variant='outlined'
            >
                Click Me
            </Button>
        </Box>
    );
};

const root = ReactDOM.createRoot(document.getElementById('root'));
root.render(
    <ThemeProvider theme={theme}>
        {/* CssBaseline kickstart an elegant, consistent, and simple baseline to build upon. */}
        <CssBaseline />
        <App />
    </ThemeProvider>
);
```
