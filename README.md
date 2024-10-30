[30/10, 3:25 pm] Meta AI: *Frontend (React Native)*
```
jsx
import React, { useState } from 'react';
import { View, Text, Button, TextInput } from 'react-native';
import axios from 'axios';

const App = () => {
  const [phone, setPhone] = useState('');
  const [password, setPassword] = useState('');
  const [name, setName] = useState('');
  const [location, setLocation] = useState('');

  const login = async () => {
    try {
      const response = await axios.post('/login', { phone, password });
      console.log(response.data);
    } catch (error) {
      console.error(error);
    }
  };

  const register = async () => {
    try {
      const response = await axios.post('/register', { name, phone, password, location });
      console.log(response.data);
    } catch (error) {
      console.error(error);
    }
  };

  const sos = async () => {
    try {
      const response = await axios.post('/sos', { phone, location });
      console.log(response.data);
    } catch (error) {
      console.error(error);
    }
  };

  return (
    <View>
      <Text>Mahila Safety App</Text>
      <TextInput placeholder="Phone Number" value={phone} onChangeText={(text) => setPhone(text)} />
      <TextInput placeholder="Password" secureTextEntry={true} value={password} onChangeText={(text) => setPassword(text)} />
      <Button title="Login" onPress={login} />
      <Button title="Register" onPress={register} />
      <Button title="SOS" onPress={s
```
[30/10, 3:25 pm] Meta AI: *Frontend (React Native)*
```
jsx
import React, { useState } from 'react';
import { View, Text, Button, TextInput } from 'react-native';
import axios from 'axios';

const App = () => {
  const [phone, setPhone] = useState('');
  const [password, setPassword] = useState('');
  const [name, setName] = useState('');
  const [location, setLocation] = useState('');

  const login = async () => {
    try {
      const response = await axios.post('/login', { phone, password });
      console.log(response.data);
    } catch (error) {
      console.error(error);
    }
  };

  const register = async () => {
    try {
      const response = await axios.post('/register', { name, phone, password, location });
      console.log(response.data);
    } catch (error) {
      console.error(error);
    }
  };

  const sos = async () => {
    try {
      const response = await axios.post('/sos
```
[30/10, 3:25 pm] Meta AI: *Frontend (React Native)*
```
jsx
import React, { useState } from 'react';
import { View, Text, Button, TextInput } from 'react-native';
import axios from 'axios';

const App = () => {
  const [phone, setPhone] = useState('');
  const [password, setPassword] = useState('');
  const [name, setName] = useState('');
  const [location, setLocation] = useState('');

  const login = async () => {
    try {
      const response = await axios.post('/login', { phone, password });
      console.log(response.data);
    } catch (error) {
      console.error(error);
    }
  };

  const register = async () => {
    try {
      const response = await axios.post('/register', { name, phone, password, location });
      console.log(response.data);
    } catch (error) {
      console.error(error);
    }
  };

  const sos = async () => {
    try {
      const response = await axios.post('/sos', { phone, location });
      console.log(response.data);
    } catch (error) {
      console.error(error);
    }
  };

  return (
    <View>
      <Text>Mahila Safety App</Text>
      <TextInput placeholder="Phone Number" value={phone} onChangeText={(text) => setPhone(text)} />
      <TextInput placeholder="Password" secureTextEntry={true} value={password} onChangeText={(text) => setPassword(text)} />
      <Button title="Login" onPress={login} />
      <Button title="Register" onPress={register} />
      <Button title="SOS" onPress={sos} />
    </View>
  );
};

export default App;
```

*Backend (Node.js)*
```
const express = require('express');
const app = express();
const mongoose = require('mongoose');
const helmet = require('helmet');

mongoose.connect('mongodb://localhost/mahilasafety', { useNewUrlParser: true, useUnifiedTopology: true });

const userSchema = new mongoose.Schema({
  name: String,
  phone: String,
  password: String,
  location: String
});

const User = mongoose.model('User', userSchema);

app.use(express.json());
app.use(express.urlencoded({ extended: true }));
app.use(helmet());

app.post('/login', (req, res) => {
  const { phone, password } = req.body;
  User.findOne({ phone }, (err, user) => {
    if (err || !user) {
      return res.status(401).send('Invalid credentials');
    }
    if (password !== user.password) {
      return res.status(401).send('Invalid credentials');
    }
    res.send('Logged in successfully');
  });
});

app.post('/register', (req, res) => {
  const { name, phone, password, location } = req.body;
  const user = new User({ name, phone, password, location });
  user.save((err) => {
    if (err) {
      return res.status(500).send('Registration failed');
    }
    res.send('Registered successfully');
  });
});

app.post('/sos', (req, res) => {
  const { phone, location } = req.body;
  // Send SOS alert to emergency services
  res.send('SOS sent');
});

app.listen(3000, () => {
  console.log('Server started on port 3000');
});
```

*Database (MongoDB)*
```
bash
use mahilasafety
create collection users
```
[30/10, 3:25 pm] Meta AI: *Frontend (React Native)*
```
jsx
import React, { useState } from 'react';
import { View, Text, Button, TextInput } from 'react-native';
import axios from 'axios';

const App = () => {
  const [phone, setPhone] = useState('');
  const [password, setPassword] = useState('');
  const [name, setName] = useState('');
  const [location, setLocation] = useState('');

  const login = async () => {
    try {
      const response = await axios.post('/login', { phone, password });
      console.log(response.data);
    } catch (error) {
      console.error(error);
    }
  };

  const register = async () => {
    try {
      const response = await axios.post('/register', { name, phone, password, location });
      console.log(response.data);
    } catch (error) {
      console.error(error);
    }
  };

  const sos = async () => {
    try {
      const response = await axios.post('/sos', { phone, location });
      console.log(response.data);
    } catch (error) {
      console.error(error);
    }
  };

  return (
    <View>
      <Text>Mahila Safety App</Text>
      <TextInput placeholder="Phone Number" value={phone} onChangeText={(text) => setPhone(text)} />
      <TextInput placeholder="Password" secureTextEntry={true} value={password} onChangeText
```
