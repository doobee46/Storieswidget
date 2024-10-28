# StoriesWidget

The `StoriesWidget` is a Flutter widget designed to display user stories in a scrollable, Instagram-like format. It supports both images and videos with an automatic linear progress indicator, customized display duration, and a seamless experience for end-users.

## Features
- Supports image and video media types.
- Automatically calculates and displays progress for each story.
- Plays videos according to their actual duration and displays images for a configurable duration.
- Automatic looping of stories and navigation to the next story upon completion.
- Manual swipe functionality for user-initiated navigation.

## Getting Started

These instructions will guide you on setting up the project locally on your machine.

### Prerequisites

- **Flutter SDK**: [Install Flutter](https://flutter.dev/docs/get-started/install) if you haven’t already.
- **Git**: [Install Git](https://git-scm.com/downloads) if you haven’t already.
- **Supabase Account**: You’ll need a Supabase project with a table to store the stories.

### Setting Up Supabase

1. **Create a Supabase Project**: Go to [Supabase](https://supabase.io/) and set up a new project.
2. **Create the `user_stories` Table**: Create a table with the following structure:
   - `user_id` (String): User ID to associate stories.
   - `media_url` (String): URL of the media file (image or video).
   - `is_video` (Boolean): Specifies if the media is a video.
3. **API Keys**: Obtain your Supabase API URL and Key from the project’s dashboard.

### Installation

1. **Clone the repository**:
   ```bash
   git clone https://github.com/your-username/StoriesWidget.git
   cd Install dependencies:
# Flutter Stories Widget

A customizable Stories widget for Flutter applications with Supabase integration, supporting both images and videos.

## Installation

1. Add the dependency to your `pubspec.yaml`:
   ```yaml
   dependencies:
     flutter_stories_widget: ^1.0.0  # Replace with actual version
   ```

2. Install dependencies:
   ```bash
   flutter pub get
   ```

## Configuration

### Supabase Setup

Create a configuration file at `lib/supabase_config.dart`:

```dart
const String SUPABASE_URL = 'your-supabase-url';
const String SUPABASE_KEY = 'your-supabase-key';
```

## Usage

### Basic Implementation

```dart
import 'package:your_package_name/widgets/stories_widget.dart';

// In your widget build method:
StoriesWidget(
  userId: 'user_id_here',  // Replace with dynamic user ID
  width: MediaQuery.of(context).size.width,
  height: MediaQuery.of(context).size.height * 0.8,
)
```

## Features

### Content Types
- **Videos**: Auto-play with natural duration
- **Images**: Display with configurable duration (default: 7 seconds)

### Components

1. **Story Class**
   - Defines story structure
   - Handles automatic video duration fetching
   - Manages media type detection

2. **StoryDisplayWidget**
   - Core functionality for story navigation
   - Handles swipe gestures
   - Manages story progression
   - Controls story looping

3. **StoryContentWidget**
   - Renders media content
   - Supports both image and video formats
   - Handles media loading states

4. **Progress Indicator**
   - Shows story progress at top of screen
   - Dynamically updates based on content type
   - Supports pause/resume functionality

## Customization

### Modifying Image Duration

To change the default image display duration, locate `_StoryDisplayWidgetState.startStoryProgress()` and modify:

```dart
final Duration imageDuration = Duration(seconds: 7);  // Adjust as needed
```

## Troubleshooting

### Common Issues

1. **Video Progress Issues**
   - Verify video duration fetching
   - Check Supabase connection
   - Ensure video URLs are accessible

2. **Supabase API Errors**
   - Verify API URL and key configuration
   - Check network connectivity
   - Validate Supabase permissions

### Debug Tips
- Enable debug logging for detailed error tracking
- Verify media URLs in Supabase storage
- Check network requests in debug console

## Contributing

We welcome contributions! Please follow these steps:

1. Fork the repository
2. Create a feature branch
3. Submit a pull request

For bug reports or feature requests, please open an issue in the repository.

## License

This project is licensed under the MIT License. See the LICENSE file for details.

---

**Note**: Remember to replace placeholder values (`your-supabase-url`, `your-supabase-key`, etc.) with your actual project configuration.




