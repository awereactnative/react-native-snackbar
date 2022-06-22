# Introduction

Snackbars provide brief feedback about an operation through a message at the bottom of the screen. Snackbar by default uses onSurface color from theme.

# Demo 

![main](https://user-images.githubusercontent.com/86215353/174958259-ccfef284-9155-4547-a9a7-9c730e814a80.gif)


# Installation

```
npm install react-native-paper --save
```

# Example

```js

import * as React from 'react';
import { View, StyleSheet } from 'react-native';
import { Button, Snackbar } from 'react-native-paper';

const App = () => {
  const [visible, setVisible] = React.useState(false);

  const onToggleSnackBar = () => setVisible(!visible);

  const onDismissSnackBar = () => setVisible(false);

  return (
    <View style={styles.container}>
      <Button
       onPress={onToggleSnackBar}>{visible ? 'Hide' : 'Show'}</Button>
      <Snackbar
        visible={visible}
        onDismiss={onDismissSnackBar}
        action={{
          label: 'Undo',
          onPress: () => {
            // Do something
          },
        }}>
        Hey there!
      </Snackbar>
    </View>
  );
};

const styles = StyleSheet.create({
  container: {
    flex: 1,
    justifyContent: "center",
    alignItems:"center",
  },
  button:{
    borderColor: "black"
    }
});

export default App;

```
