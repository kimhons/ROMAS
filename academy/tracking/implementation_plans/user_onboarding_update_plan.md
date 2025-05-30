# User Onboarding Experience Update Plan

## Overview

This document outlines the detailed implementation plan for updating the user onboarding experience in the Radiation Oncology Academy mobile app. The updated onboarding will set appropriate expectations about our phased content release approach, highlight available content, and create excitement about upcoming features.

## Current Onboarding Analysis

### Strengths
- Clean, professional visual design
- Efficient account creation process
- Clear explanation of app purpose
- Effective permission requests

### Limitations
- No explanation of phased content release strategy
- Unclear which content is currently available
- No introduction to the content roadmap feature
- Limited personalization based on user role/interests
- No guidance on how to use interactive features

## Updated Onboarding Design

### Flow Overview
1. **Welcome Screen**: App introduction and value proposition
2. **Account Creation/Login**: User authentication
3. **Role Selection**: User identifies professional role
4. **Interest Selection**: User selects topics of interest
5. **Available Content Showcase**: Highlight currently available modules
6. **Coming Soon Preview**: Introduction to upcoming content
7. **Content Roadmap Introduction**: Explanation of phased release approach
8. **Feature Tour**: Introduction to key app features
9. **Notification Preferences**: Settings for content updates
10. **Home Screen**: Transition to main app experience

### Screen-by-Screen Specifications

#### 1. Welcome Screen
- **Content**: Brief introduction to Radiation Oncology Academy
- **Visual**: Professional imagery related to radiation oncology
- **Action**: "Get Started" button
- **Updates Needed**: Refresh messaging to mention "growing content library"

#### 2. Account Creation/Login
- **Content**: Authentication options
- **Visual**: Form fields with clean layout
- **Action**: Create account or login
- **Updates Needed**: No significant changes required

#### 3. Role Selection (New Screen)
- **Content**: "Select your professional role"
- **Visual**: Card-based selection of roles:
  - Radiation Oncologist
  - Medical Physicist
  - Dosimetrist
  - Radiation Therapist
  - Resident/Fellow
  - Student
  - Other
- **Action**: Tap to select role
- **Purpose**: Personalize content recommendations

#### 4. Interest Selection (New Screen)
- **Content**: "Select topics of interest"
- **Visual**: Multi-select grid of topics:
  - Radiation Biology
  - Radiation Physics
  - Radiation Protection
  - Treatment Planning
  - Clinical Applications
  - Professional Practice
- **Action**: Tap multiple topics
- **Purpose**: Prioritize content in roadmap and recommendations

#### 5. Available Content Showcase (New Screen)
- **Content**: "Available now in Radiation Oncology Academy"
- **Visual**: Carousel of available modules with brief descriptions
- **Action**: Swipe through available content
- **Purpose**: Set clear expectations about current content

#### 6. Coming Soon Preview (New Screen)
- **Content**: "Coming soon to Radiation Oncology Academy"
- **Visual**: Preview cards for upcoming modules with release timeframes
- **Action**: Swipe through upcoming content
- **Purpose**: Generate excitement about future releases

#### 7. Content Roadmap Introduction (New Screen)
- **Content**: "Our content roadmap"
- **Visual**: Simplified version of content roadmap
- **Action**: "View Full Roadmap" button
- **Purpose**: Introduce roadmap feature and set expectations

#### 8. Feature Tour (New Screen)
- **Content**: "Key features to enhance your learning"
- **Visual**: Carousel of feature highlights:
  - Interactive Diagrams
  - Knowledge Checks
  - Offline Access
  - Progress Tracking
  - Content Roadmap
- **Action**: Swipe through features
- **Purpose**: Highlight app capabilities

#### 9. Notification Preferences (New Screen)
- **Content**: "Stay updated on new content"
- **Visual**: Toggle options for different notification types:
  - New content releases
  - Content previews
  - Updates to topics of interest
  - Learning reminders
- **Action**: Set notification preferences
- **Purpose**: Engage users with future content

#### 10. Home Screen Transition
- **Content**: "You're all set!"
- **Visual**: Animation transitioning to home screen
- **Action**: Automatic transition after brief delay
- **Purpose**: Smooth transition to main app experience

## Technical Implementation

### Component Structure

#### OnboardingNavigator
```javascript
const OnboardingNavigator = () => {
  return (
    <Stack.Navigator headerMode="none">
      <Stack.Screen name="Welcome" component={WelcomeScreen} />
      <Stack.Screen name="Auth" component={AuthScreen} />
      <Stack.Screen name="RoleSelection" component={RoleSelectionScreen} />
      <Stack.Screen name="InterestSelection" component={InterestSelectionScreen} />
      <Stack.Screen name="AvailableContent" component={AvailableContentScreen} />
      <Stack.Screen name="ComingSoonPreview" component={ComingSoonPreviewScreen} />
      <Stack.Screen name="RoadmapIntro" component={RoadmapIntroScreen} />
      <Stack.Screen name="FeatureTour" component={FeatureTourScreen} />
      <Stack.Screen name="NotificationPreferences" component={NotificationPreferencesScreen} />
      <Stack.Screen name="OnboardingComplete" component={OnboardingCompleteScreen} />
    </Stack.Navigator>
  );
};
```

#### RoleSelectionScreen
```javascript
const RoleSelectionScreen = ({ navigation }) => {
  const [selectedRole, setSelectedRole] = useState(null);
  const dispatch = useDispatch();
  
  const roles = [
    { id: 'radiation_oncologist', title: 'Radiation Oncologist', icon: 'doctor' },
    { id: 'medical_physicist', title: 'Medical Physicist', icon: 'atom' },
    { id: 'dosimetrist', title: 'Dosimetrist', icon: 'calculator' },
    { id: 'radiation_therapist', title: 'Radiation Therapist', icon: 'radiation' },
    { id: 'resident', title: 'Resident/Fellow', icon: 'school' },
    { id: 'student', title: 'Student', icon: 'book' },
    { id: 'other', title: 'Other', icon: 'account' }
  ];
  
  const handleRoleSelect = (roleId) => {
    setSelectedRole(roleId);
    dispatch(setUserRole(roleId));
  };
  
  const handleContinue = () => {
    if (selectedRole) {
      navigation.navigate('InterestSelection');
    }
  };
  
  return (
    <View style={styles.container}>
      <View style={styles.header}>
        <Text style={styles.title}>Select your professional role</Text>
        <Text style={styles.subtitle}>
          We'll personalize your experience based on your role
        </Text>
      </View>
      
      <FlatList
        data={roles}
        numColumns={2}
        keyExtractor={(item) => item.id}
        renderItem={({ item }) => (
          <TouchableOpacity
            style={[
              styles.roleCard,
              selectedRole === item.id && styles.selectedRoleCard
            ]}
            onPress={() => handleRoleSelect(item.id)}
          >
            <Icon name={item.icon} size={40} color="#0066cc" />
            <Text style={styles.roleTitle}>{item.title}</Text>
          </TouchableOpacity>
        )}
        contentContainerStyle={styles.rolesGrid}
      />
      
      <View style={styles.footer}>
        <TouchableOpacity
          style={[
            styles.continueButton,
            !selectedRole && styles.continueButtonDisabled
          ]}
          onPress={handleContinue}
          disabled={!selectedRole}
        >
          <Text style={styles.continueButtonText}>Continue</Text>
        </TouchableOpacity>
      </View>
    </View>
  );
};
```

#### AvailableContentScreen
```javascript
const AvailableContentScreen = ({ navigation }) => {
  const availableModules = useSelector(state => 
    state.content.modules.filter(module => module.status === 'available' || module.status === 'partial')
  );
  
  const renderModuleCard = ({ item }) => (
    <View style={styles.moduleCard}>
      <Image source={item.coverImage} style={styles.moduleCover} />
      <View style={styles.moduleInfo}>
        <Text style={styles.moduleTitle}>{item.title}</Text>
        <Text style={styles.moduleDescription}>{item.description}</Text>
        {item.status === 'partial' && (
          <View style={styles.partialBadge}>
            <Text style={styles.partialBadgeText}>Partially Available</Text>
          </View>
        )}
      </View>
    </View>
  );
  
  return (
    <View style={styles.container}>
      <View style={styles.header}>
        <Text style={styles.title}>Available Now</Text>
        <Text style={styles.subtitle}>
          Start learning with these comprehensive modules
        </Text>
      </View>
      
      <Carousel
        data={availableModules}
        renderItem={renderModuleCard}
        sliderWidth={screenWidth}
        itemWidth={screenWidth * 0.8}
        inactiveSlideScale={0.9}
        inactiveSlideOpacity={0.7}
        containerCustomStyle={styles.carousel}
      />
      
      <View style={styles.footer}>
        <TouchableOpacity
          style={styles.continueButton}
          onPress={() => navigation.navigate('ComingSoonPreview')}
        >
          <Text style={styles.continueButtonText}>See What's Coming</Text>
        </TouchableOpacity>
      </View>
    </View>
  );
};
```

#### ComingSoonPreviewScreen
```javascript
const ComingSoonPreviewScreen = ({ navigation }) => {
  const upcomingModules = useSelector(state => 
    state.content.modules.filter(module => 
      module.status === 'in_development' || module.status === 'coming_soon'
    )
  );
  
  const renderModuleCard = ({ item }) => (
    <View style={styles.moduleCard}>
      <Image source={item.coverImage} style={styles.moduleCover} />
      <View style={styles.moduleInfo}>
        <Text style={styles.moduleTitle}>{item.title}</Text>
        <Text style={styles.moduleDescription}>{item.description}</Text>
        <View style={styles.statusContainer}>
          <Text style={styles.statusText}>
            {item.status === 'in_development' ? 'In Development' : 'Coming Soon'}
          </Text>
          {item.estimatedRelease && (
            <Text style={styles.releaseDate}>Expected: {item.estimatedRelease}</Text>
          )}
        </View>
      </View>
    </View>
  );
  
  return (
    <View style={styles.container}>
      <View style={styles.header}>
        <Text style={styles.title}>Coming Soon</Text>
        <Text style={styles.subtitle}>
          Preview our upcoming educational content
        </Text>
      </View>
      
      <Carousel
        data={upcomingModules}
        renderItem={renderModuleCard}
        sliderWidth={screenWidth}
        itemWidth={screenWidth * 0.8}
        inactiveSlideScale={0.9}
        inactiveSlideOpacity={0.7}
        containerCustomStyle={styles.carousel}
      />
      
      <View style={styles.footer}>
        <TouchableOpacity
          style={styles.continueButton}
          onPress={() => navigation.navigate('RoadmapIntro')}
        >
          <Text style={styles.continueButtonText}>Learn About Our Roadmap</Text>
        </TouchableOpacity>
      </View>
    </View>
  );
};
```

#### RoadmapIntroScreen
```javascript
const RoadmapIntroScreen = ({ navigation }) => {
  return (
    <View style={styles.container}>
      <View style={styles.header}>
        <Text style={styles.title}>Content Roadmap</Text>
        <Text style={styles.subtitle}>
          Our plan for expanding the Radiation Oncology Academy
        </Text>
      </View>
      
      <View style={styles.roadmapPreview}>
        <Image 
          source={require('../assets/images/roadmap_preview.png')} 
          style={styles.roadmapImage} 
          resizeMode="contain"
        />
        
        <View style={styles.roadmapInfo}>
          <Text style={styles.roadmapText}>
            Radiation Oncology Academy is constantly growing. Our content roadmap
            shows you what's available now and what's coming in the future.
          </Text>
          
          <Text style={styles.roadmapText}>
            You can access the full roadmap anytime from the home screen or
            settings menu, and even opt-in for notifications when new content
            is released.
          </Text>
        </View>
      </View>
      
      <View style={styles.footer}>
        <TouchableOpacity
          style={styles.viewRoadmapButton}
          onPress={() => {
            // Store that user has seen roadmap intro
            AsyncStorage.setItem('hasSeenRoadmapIntro', 'true');
            navigation.navigate('FeatureTour');
          }}
        >
          <Text style={styles.viewRoadmapButtonText}>Continue</Text>
        </TouchableOpacity>
      </View>
    </View>
  );
};
```

### Redux Store Updates

#### User Preferences Slice
```javascript
// userSlice.js
import { createSlice } from '@reduxjs/toolkit';

const initialState = {
  role: null,
  interests: [],
  hasCompletedOnboarding: false,
  notificationPreferences: {
    contentReleases: true,
    contentPreviews: true,
    interestUpdates: true,
    learningReminders: false
  }
};

const userSlice = createSlice({
  name: 'user',
  initialState,
  reducers: {
    setUserRole: (state, action) => {
      state.role = action.payload;
    },
    setUserInterests: (state, action) => {
      state.interests = action.payload;
    },
    setNotificationPreferences: (state, action) => {
      state.notificationPreferences = {
        ...state.notificationPreferences,
        ...action.payload
      };
    },
    completeOnboarding: (state) => {
      state.hasCompletedOnboarding = true;
    }
  }
});

export const { 
  setUserRole, 
  setUserInterests, 
  setNotificationPreferences,
  completeOnboarding
} = userSlice.actions;

export default userSlice.reducer;
```

### Navigation Integration

#### App.js Updates
```javascript
// App.js
import React, { useEffect, useState } from 'react';
import { NavigationContainer } from '@react-navigation/native';
import { createStackNavigator } from '@react-navigation/stack';
import { useSelector, useDispatch } from 'react-redux';
import AsyncStorage from '@react-native-async-storage/async-storage';

import OnboardingNavigator from './navigation/OnboardingNavigator';
import MainNavigator from './navigation/MainNavigator';
import { completeOnboarding } from './redux/userSlice';

const Stack = createStackNavigator();

const App = () => {
  const [isLoading, setIsLoading] = useState(true);
  const hasCompletedOnboarding = useSelector(state => state.user.hasCompletedOnboarding);
  const dispatch = useDispatch();
  
  useEffect(() => {
    // Check if user has completed onboarding
    const checkOnboardingStatus = async () => {
      try {
        const value = await AsyncStorage.getItem('hasCompletedOnboarding');
        if (value === 'true') {
          dispatch(completeOnboarding());
        }
      } catch (error) {
        console.log('Error checking onboarding status:', error);
      } finally {
        setIsLoading(false);
      }
    };
    
    checkOnboardingStatus();
  }, [dispatch]);
  
  if (isLoading) {
    return <SplashScreen />;
  }
  
  return (
    <NavigationContainer>
      <Stack.Navigator headerMode="none">
        {!hasCompletedOnboarding ? (
          <Stack.Screen name="Onboarding" component={OnboardingNavigator} />
        ) : (
          <Stack.Screen name="Main" component={MainNavigator} />
        )}
      </Stack.Navigator>
    </NavigationContainer>
  );
};

export default App;
```

### Visual Design Updates

#### Style Guidelines
- **Color Palette**: Maintain existing app colors with emphasis on primary blue
- **Typography**: Consistent font hierarchy across all screens
- **Imagery**: Professional medical imagery with focus on radiation oncology
- **Animations**: Subtle transitions between screens
- **Illustrations**: Custom illustrations for feature explanations

#### Design Assets Needed
- Role selection icons (7 icons)
- Interest topic illustrations (6 il
(Content truncated due to size limit. Use line ranges to read in chunks)