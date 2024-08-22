THE RESTAURANT APP  

  

HELLO! 

 

Welcome to the Restaurant App, made for a restaurant as a digital menu, where customers can order food based on the menu provided. 

 

 

DESIGNING OF THE USER INTERFACE 

 

Welcome Screen 

 

   The “Welcome Screen” will have a simple design with an image on top using <Image source={require(‘./Assets/image.jpg)} /> with import { Image } from ‘react-native’ also with const styles “stylesheet” to place it in position. 

 

It has a welcome message and a press button instruction after the image. 

The button saying, “Next Page”, colored in purple using the const styles Stylesheet, <TouchableOpacity> tag which enables the styling of the button as <button /> tag in react native only allows the changing color of the button, not fully styling it. 

 

The button can take the user to the next page by:  

 

          a. Install navigation page dependencies: 

             npm install @react-navigation/native @react-navigation/native-stack (Stack). 

                   (Installing Screen) 

                  If expo: npx expo install react-native-screens react-native-safe-area-context 

                  If bare: npm install react-native-screens react-native-safe-area-context 

           

         b. Import navigation page dependencies: 

              import {NavigationContainer} from '@react-navigation/native'; 
                    import {createNativeStackNavigator} from '@react-navigation/native-stack'; 

 

          c. Usage of dependencies:   

                 const Stack = createNativeStackNavigator(); 
 
               export default App () { 
  

                      return ( 
                           <NavigationContainer> 
                          <Stack.Navigator> 
                         <Stack.Screen name="Home" component={HomeScreen} /> 
                         <Stack.Screen name="Profile" component={ProfileScreen} /> 
                        </Stack.Navigator> 
                        </NavigationContainer> 
                    ); 
              }; 

             

             function WelcomePage({ navigation }) { 

  return ( 

    <View> 

      <SafeAreaView> 

        <ScrollView> 

              <View style={styles.container}> 

                   <Image source={require('./assets/RestaurantLogo.jpg')} /> 

              </View> 

 

               <View> 

                   <Text style={styles.title}>Welcome to the Restaurant App</Text> 

              </View> 

 

             <View> 

                     <Text>{'\n'}</Text> 

                    <Text style={styles.titleText}>Press the "Next Page" Button to access our menu</Text> 

              </View> 

 

              <View> 

                      <TouchableOpacity style={styles.nextPageButton} onPress={() => { navigation.navigate('Home') }}> 

                               <Text style={styles.nextPageText}>Next Page</Text> 

                      </TouchableOpacity> 

              </View> 

        </ScrollView> 

      </SafeAreaView> 

   </View> 

 

 

 

         

 

Import { View, Image, Stylesheet, Text, TouchableOpacity } from ‘./react-native’ 

 

 

 

 

Home Screen 

 

   The “Home Screen” will be designed like a real-life menu with images, names, description and price and the course name on top. 

 

It is only visual as no coding takes place on this page. 

 

The course name with the number of items [6] will appear in text. 

 

   Of each course, the visual of these courses will be made by: 

            a. Make a background by using a <Text> tag and placing a “\n”                    endline escape sequence and styling it.  

               Code:                                         

            <View>                                                              

                   <Text>{'\n'}</Text> 

            </View> 

 

                Style: 

               Background: {                                                                                              

                        padding: 5, 

                      borderBlockColor: '000000', 

                       borderRadius: 10, 

                       borderWidth: 2, 

                    }, 

 

                 b. Place Image on the left first inside the background then the text     (name, description, price) 

 

 

                      Code: 

<View style={styles.Background}> 

           

              <View style={styles.Image}> 

                <Image source={require('./assets/LoadedDevliledEggs.jpg')}/> 

              </View> 

 

              <View> 

                <Text style={styles.deviledEggsText}>Name: Deviled Eggs {'\n'}  

                    Description: It is deviled Eggs 

                </Text> 

              </View> 

</View> 

 

 

                  Style: 

 

                       Image: { 

                            borderRadius: 25, 

                            borderBlockColor: '000000', 

                            marginHorizontal: 5, 

                            marginVertical: 8, 

                            resizeMode: 'contain' 

                        }, 

 

                         Text: { 

                             position: 'absolute', 

                              top: -100, 

                               left: 100, 

                               fontSize: 16, 

                            }, 

                                                                                   

                                                                                           

 

  

 

The other meals and courses will have the same codes and styling shown  above.  

 

Afterwards the button is displayed to go to the next page “Order Menu”. 

 

        <View> 

                      <TouchableOpacity style={styles.nextPageButton} onPress={() => { navigation.navigate('Order') }}> 

                               <Text style={styles.nextPageText}>Start Ordering</Text> 

                      </TouchableOpacity> 

              </View> 

       

 

Import { View, Image, Stylesheet, Text, TouchableOpacity } from ‘./react-native’. 

 

 

 

 

3.Order Menu Screen 

 

  The “Order Menu Screen” will display a list of items the user orders.  

each course average price of each course based on number of items ordered and its prices added together. 

 

Two buttons (Add Food Items and Filter by course) were also added. 

 

The two buttons used will be styled almost similar to the react native <button /> and the <TouchableOpacity> tag will be used. 

 

The button can take the user to the next page by (explain in the welcome page and Home Page)          

 

Import { View, Image, Stylesheet, Text, TouchableOpacity } from ‘./react-native’. 

 

 

4. Add Items Screen 

 

The “Add Items Screen” consists of Text Input Box where the user must fill in (fill in message might be displayed), after which the user clicks the “Add Item button” to send data to the order menu screen where it will show the items ordered. 

 

A select box will be added for the user to choose the course they want . 

 

The select box in react-native is added in a form of a “Picker” using a <Picker> tag. For it to work, dependencies must be installed. 

 

  a. Install Picker dependencies: 

        npm i @react-native-picker/picker 

 

 b. Import Picker dependencies: 

        import { Picker } from "@react-native-picker/picker"; 

 

 c. Usage of Picker: 

        <Picker selectedValue={this.state.language} style={{ height: 50, width: 100 }} onValueChange={(itemValue, itemIndex) => this.setState({ language: itemValue }) }>  

              <Picker.Item label="Java" value="java" />  

             <Picker.Item label="JavaScript" value="js" />  

        </Picker> 

 

 Import { View, Stylesheet, Text, TextInput, TouchableOpacity } from ‘./react-native’ 

 

Import { Picker } from "@react-native-picker/picker";  

 

 

5.Filter Screen 

The “Filter Screen” only displays which food item falls under a type of course. This page can only show you which food item falls under which course type.       

 

Import { View, Stylesheet, Text } from ‘./react-native’ 

 

GitHub Link: https://github.com/IIEWFL/mast5112-part-1-Bophelo-G-THWALA.git 

 

 

References 

 

Images for food items 

 

Obtained from: Partstown 

 

Link: https://www.partstown.com/about-us/five-course-meal-ideas-for-restaurants 

 

 

Picker Dependencies 

 

Obtained from: React-native and npm 

 

Link: 

 React-native: https://archive.reactnative.dev/docs/picker 

 

Npm (install depencies): https://www.npmjs.com/package/@react-native-picker/picker 

 
