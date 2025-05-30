# Coming Soon Indicators and Content Roadmap Implementation Plan

## Overview

This document outlines the detailed implementation plan for adding "Coming Soon" indicators and a content roadmap to the Radiation Oncology Academy mobile app. These features are critical for our phased content release strategy, setting appropriate user expectations while generating excitement for upcoming content.

## Coming Soon Indicators

### Design Specifications

#### Visual Design
- **Style**: Consistent with app's design language
- **Color Scheme**: Muted version of app's primary colors (blue/teal)
- **Typography**: Same font family as app (Helvetica Neue/Roboto)
- **Badge Design**: Semi-transparent overlay with "Coming Soon" text
- **Icon**: Clock or calendar icon to reinforce future availability

#### Placement
1. **Module Cards**: Overlay on module cards for unreleased modules
2. **Section Lists**: Indicator next to section names for upcoming content
3. **Navigation Menu**: Visual distinction for upcoming sections
4. **Search Results**: Clear indication when search returns upcoming content

#### States and Variations
1. **Coming Soon**: For content planned but not yet in development
2. **In Development**: For content actively being developed
3. **Preview Available**: For content with sample materials available

### Technical Implementation

#### Module Card Component Modification
```javascript
const ModuleCard = ({ module }) => {
  const isAvailable = module.status === 'available';
  
  return (
    <TouchableOpacity 
      style={styles.card}
      onPress={() => isAvailable ? navigateToModule(module.id) : showRoadmapModal(module.id)}
      disabled={!isAvailable && !module.previewAvailable}
    >
      <Image source={module.coverImage} style={styles.coverImage} />
      <View style={styles.contentContainer}>
        <Text style={styles.title}>{module.title}</Text>
        <Text style={styles.description}>{module.description}</Text>
        
        {!isAvailable && (
          <View style={styles.comingSoonBadge}>
            <Icon name="clock-outline" size={16} color="#fff" />
            <Text style={styles.comingSoonText}>
              {module.status === 'in_development' ? 'In Development' : 'Coming Soon'}
            </Text>
            {module.estimatedRelease && (
              <Text style={styles.releaseDate}>{module.estimatedRelease}</Text>
            )}
          </View>
        )}
        
        {!isAvailable && module.previewAvailable && (
          <TouchableOpacity 
            style={styles.previewButton}
            onPress={() => navigateToModulePreview(module.id)}
          >
            <Text style={styles.previewButtonText}>Preview Available</Text>
          </TouchableOpacity>
        )}
      </View>
    </TouchableOpacity>
  );
};
```

#### Section List Component Modification
```javascript
const SectionListItem = ({ section, moduleId }) => {
  const isAvailable = section.status === 'available';
  
  return (
    <TouchableOpacity 
      style={[styles.sectionItem, !isAvailable && styles.sectionItemDisabled]}
      onPress={() => isAvailable ? navigateToSection(moduleId, section.id) : showRoadmapModal(moduleId, section.id)}
      disabled={!isAvailable && !section.previewAvailable}
    >
      <View style={styles.sectionInfo}>
        <Text style={styles.sectionTitle}>{section.title}</Text>
        <Text style={styles.sectionDescription}>{section.description}</Text>
        
        {!isAvailable && (
          <View style={styles.sectionStatusBadge}>
            <Text style={styles.statusText}>
              {section.status === 'in_development' ? 'In Development' : 'Coming Soon'}
            </Text>
            {section.estimatedRelease && (
              <Text style={styles.sectionReleaseDate}>{section.estimatedRelease}</Text>
            )}
          </View>
        )}
      </View>
      
      <View style={styles.sectionAccessory}>
        {isAvailable ? (
          <Icon name="chevron-right" size={24} color="#0066cc" />
        ) : section.previewAvailable ? (
          <TouchableOpacity onPress={() => navigateToSectionPreview(moduleId, section.id)}>
            <Text style={styles.previewText}>Preview</Text>
          </TouchableOpacity>
        ) : (
          <Icon name="clock-outline" size={24} color="#8e8e93" />
        )}
      </View>
    </TouchableOpacity>
  );
};
```

#### Search Results Modification
```javascript
const SearchResultItem = ({ result }) => {
  const isAvailable = result.status === 'available';
  
  return (
    <TouchableOpacity 
      style={styles.searchResult}
      onPress={() => isAvailable ? navigateToResult(result) : showRoadmapModal(result.moduleId, result.sectionId)}
      disabled={!isAvailable && !result.previewAvailable}
    >
      <Text style={styles.resultTitle}>{result.title}</Text>
      <Text style={styles.resultContext}>{result.context}</Text>
      
      {!isAvailable && (
        <View style={styles.resultStatusBadge}>
          <Text style={styles.resultStatusText}>
            {result.status === 'in_development' ? 'In Development' : 'Coming Soon'}
          </Text>
        </View>
      )}
    </TouchableOpacity>
  );
};
```

### Data Structure Updates

#### Module Status Schema
```javascript
// In contentSlice.js
const initialState = {
  modules: [
    {
      id: 'radiation_protection',
      title: 'Radiation Protection',
      description: 'Comprehensive coverage of radiation safety protocols and requirements',
      status: 'available',
      coverImage: require('../assets/images/radiation_protection_cover.jpg'),
      sections: [
        // Section data
      ]
    },
    {
      id: 'radiation_biology',
      title: 'Radiation Biology',
      description: 'Fundamental principles and clinical applications of radiation biology',
      status: 'partial', // Partially available
      estimatedCompletion: 'June 2025',
      coverImage: require('../assets/images/radiation_biology_cover.jpg'),
      sections: [
        // Section data with individual status
      ]
    },
    {
      id: 'radiation_physics',
      title: 'Radiation Physics',
      description: 'Physical principles of radiation and their applications in oncology',
      status: 'in_development',
      estimatedRelease: 'July 2025',
      previewAvailable: true,
      coverImage: require('../assets/images/radiation_physics_cover.jpg'),
      sections: [
        // Section data
      ]
    },
    {
      id: 'clinical_applications',
      title: 'Clinical Applications',
      description: 'Practical applications of radiation oncology principles in clinical settings',
      status: 'coming_soon',
      estimatedRelease: 'September 2025',
      previewAvailable: false,
      coverImage: require('../assets/images/clinical_applications_cover.jpg'),
      sections: [
        // Section data
      ]
    }
  ],
  // Other state properties
};
```

#### Section Status Schema
```javascript
// Example of Radiation Biology Module sections with status
{
  id: 'radiation_biology',
  title: 'Radiation Biology',
  description: 'Fundamental principles and clinical applications of radiation biology',
  status: 'partial',
  estimatedCompletion: 'June 2025',
  coverImage: require('../assets/images/radiation_biology_cover.jpg'),
  sections: [
    {
      id: 'fundamentals',
      title: 'Fundamentals of Radiation Biology',
      description: 'Basic principles and mechanisms of radiation interactions with biological systems',
      status: 'available',
      progress: 100,
      subsections: [
        // Subsection data
      ]
    },
    {
      id: 'cell_survival',
      title: 'Cell Survival Kinetics',
      description: 'Mathematical models and experimental approaches to cell survival after radiation',
      status: 'available',
      progress: 100,
      subsections: [
        // Subsection data
      ]
    },
    {
      id: 'tumor_radiobiology',
      title: 'Tumor Radiobiology',
      description: 'Radiation response of tumors and factors affecting treatment outcomes',
      status: 'in_development',
      estimatedRelease: 'May 2025',
      progress: 30,
      previewAvailable: true,
      subsections: [
        // Subsection data
      ]
    },
    {
      id: 'normal_tissue',
      title: 'Normal Tissue Effects',
      description: 'Radiation response of normal tissues and organs at risk',
      status: 'coming_soon',
      estimatedRelease: 'June 2025',
      progress: 0,
      previewAvailable: false,
      subsections: [
        // Subsection data
      ]
    }
    // Additional sections
  ]
}
```

### Implementation Timeline
- Component modifications: 3 hours
- Data structure updates: 2 hours
- Styling and visual design: 2 hours
- Testing across all app sections: 2 hours
- **Total: 9 hours**

## Content Roadmap Feature

### Design Specifications

#### Visual Design
- **Style**: Timeline-based visual representation
- **Color Scheme**: App's primary colors with clear status indicators
- **Typography**: Emphasis on release dates and content titles
- **Layout**: Scrollable timeline with module/section cards
- **Interaction**: Expandable cards for additional details

#### Content Elements
1. **Timeline Header**: "Content Roadmap" with brief explanation
2. **Module/Section Cards**: Visual representation of upcoming content
3. **Release Dates**: Estimated availability dates
4. **Progress Indicators**: Visual representation of development progress
5. **Preview Buttons**: For content with available previews
6. **Notification Options**: Allow users to opt-in for release notifications

#### Access Points
1. **Home Screen**: Dedicated "Roadmap" button in main navigation
2. **Module Screen**: "See What's Coming" button at bottom of module list
3. **Coming Soon Taps**: Tapping any "Coming Soon" indicator
4. **Settings Menu**: "Content Roadmap" option

### Technical Implementation

#### Roadmap Screen Component
```javascript
const ContentRoadmap = () => {
  const [expandedItems, setExpandedItems] = useState([]);
  const [notificationPreferences, setNotificationPreferences] = useState({});
  const modules = useSelector(state => state.content.modules);
  
  const toggleItemExpansion = (itemId) => {
    if (expandedItems.includes(itemId)) {
      setExpandedItems(expandedItems.filter(id => id !== itemId));
    } else {
      setExpandedItems([...expandedItems, itemId]);
    }
  };
  
  const toggleNotification = (itemId) => {
    setNotificationPreferences({
      ...notificationPreferences,
      [itemId]: !notificationPreferences[itemId]
    });
    // Save to user preferences
    saveNotificationPreference(itemId, !notificationPreferences[itemId]);
  };
  
  const renderTimelineItem = (item, itemType) => {
    const isExpanded = expandedItems.includes(item.id);
    const hasNotification = notificationPreferences[item.id];
    
    return (
      <View style={styles.timelineItem}>
        <View style={styles.timelineConnector} />
        
        <TouchableOpacity 
          style={[styles.itemCard, getStatusStyle(item.status)]}
          onPress={() => toggleItemExpansion(item.id)}
        >
          <View style={styles.itemHeader}>
            <Text style={styles.itemTitle}>{item.title}</Text>
            <Text style={styles.itemType}>{itemType}</Text>
            <Icon 
              name={isExpanded ? "chevron-up" : "chevron-down"} 
              size={20} 
              color="#0066cc" 
            />
          </View>
          
          <Text style={styles.itemDescription}>{item.description}</Text>
          
          <View style={styles.itemMeta}>
            <Text style={styles.statusText}>{getStatusText(item.status)}</Text>
            {item.estimatedRelease && (
              <Text style={styles.releaseDate}>Expected: {item.estimatedRelease}</Text>
            )}
          </View>
          
          {item.progress !== undefined && (
            <View style={styles.progressContainer}>
              <View 
                style={[styles.progressBar, { width: `${item.progress}%` }]} 
              />
              <Text style={styles.progressText}>{item.progress}% Complete</Text>
            </View>
          )}
          
          {isExpanded && (
            <View style={styles.expandedContent}>
              {item.previewAvailable && (
                <TouchableOpacity 
                  style={styles.previewButton}
                  onPress={() => navigateToPreview(item.id, itemType)}
                >
                  <Text style={styles.previewButtonText}>View Preview</Text>
                </TouchableOpacity>
              )}
              
              <TouchableOpacity 
                style={styles.notificationButton}
                onPress={() => toggleNotification(item.id)}
              >
                <Icon 
                  name={hasNotification ? "bell" : "bell-outline"} 
                  size={20} 
                  color={hasNotification ? "#0066cc" : "#8e8e93"} 
                />
                <Text style={styles.notificationText}>
                  {hasNotification ? "Notifications On" : "Notify Me on Release"}
                </Text>
              </TouchableOpacity>
              
              {item.features && (
                <View style={styles.featuresList}>
                  <Text style={styles.featuresHeader}>Planned Features:</Text>
                  {item.features.map((feature, index) => (
                    <Text key={index} style={styles.featureItem}>• {feature}</Text>
                  ))}
                </View>
              )}
            </View>
          )}
        </TouchableOpacity>
      </View>
    );
  };
  
  return (
    <ScrollView style={styles.container}>
      <View style={styles.header}>
        <Text style={styles.title}>Content Roadmap</Text>
        <Text style={styles.subtitle}>
          Our development plan for upcoming educational content
        </Text>
      </View>
      
      <View style={styles.timeline}>
        {modules.map(module => {
          if (module.status === 'available') return null;
          
          return (
            <View key={module.id}>
              {renderTimelineItem(module, 'Module')}
              
              {expandedItems.includes(module.id) && module.sections && 
                module.sections
                  .filter(section => section.status !== 'available')
                  .map(section => (
                    <View key={section.id} style={styles.nestedItem}>
                      {renderTimelineItem(section, 'Section')}
                    </View>
                  ))
              }
            </View>
          );
        })}
        
        <View style={styles.timelineEnd}>
          <Text style={styles.timelineEndText}>More content coming soon!</Text>
        </View>
      </View>
    </ScrollView>
  );
};
```

#### Roadmap Modal Component
```javascript
const RoadmapModal = ({ visible, onClose, focusedItemId, itemType }) => {
  const [expandedItems, setExpandedItems] = useState([focusedItemId]);
  const modules = useSelector(state => state.content.modules);
  
  // Find the focused item
  let focusedItem = null;
  let parentModule = null;
  
  if (itemType === 'module') {
    focusedItem = modules.find(module => module.id === focusedItemId);
  } else if (itemType === 'section') {
    for (const module of modules) {
      const section = module.sections.find(section => section.id === focusedItemId);
      if (section) {
        focusedItem = section;
        parentModule = module;
        break;
      }
    }
  }
  
  if (!focusedItem) return null;
  
  return (
    <Modal
      visible={visible}
      animationType="slide"
      transparent={true}
      onRequestClose={onClose}
    >
      <View style={styles.modalContainer}>
        <View style={styles.modalContent}>
          <View style={styles.modalHeader}>
            <Text style={styles.modalTitle}>Coming Soon</Text>
            <TouchableOpacity onPress={onClose}>
              <Icon name="c
(Content truncated due to size limit. Use line ranges to read in chunks)