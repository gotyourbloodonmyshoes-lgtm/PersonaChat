```markdown
# PersonaChat 🎭

An AI-powered chat application where you can talk to diverse AI characters with unique personalities. Select any character, start chatting, and enjoy realistic, engaging conversations with accurate personas.

## Features ✨

- **Character Selection**: Browse and search through 8+ unique characters
- **Accurate Personas**: Each character has detailed personality traits and response patterns
- **Long, Natural Conversations**: Characters respond with flowing, realistic sentences
- **Roleplay Support**: Uses `"quotes"` for dialogue and `*asterisks*` for actions
- **NSFW Support**: Some characters marked as NSFW-enabled for mature conversations
- **Search Functionality**: Find characters by name, role, or description
- **Real-time Chat**: Instant message delivery with typing indicators
- **Mobile Responsive**: Works seamlessly on desktop, tablet, and mobile devices
- **Beautiful UI**: Modern gradient design with smooth animations

## Tech Stack 🛠️

**Frontend:**
- React 18
- Lucide Icons
- Axios
- CSS3

**Backend:**
- Node.js & Express
- OpenAI API (GPT-4o-mini)
- CORS

## Installation 📦

### Prerequisites
- Node.js 16+
- npm or yarn
- OpenAI API key

### Setup

1. **Clone the repository**
```bash
git clone https://github.com/gotyourbloodonmyshoes-lgtm/PersonaChat.git
cd PersonaChat
```

2. **Install dependencies**
```bash
# Install client dependencies
npm install

# Install server dependencies
cd server
npm install
cd ..
```

3. **Configure environment variables**
```bash
cp .env.example .env
```

4. **Add your OpenAI API key**
```bash
# Edit .env file and add your key
OPENAI_API_KEY=sk-your-api-key-here
```

## Running the App 🚀

### Development Mode

```bash
# Terminal 1 - Start the server
cd server
npm run dev

# Terminal 2 - Start the client
npm start
```

The app will be available at `http://localhost:3000` with the backend running on `http://localhost:5000`.

### Production Build

```bash
# Build the client
npm run build

# Start the server in production
cd server
npm start
```

## Characters 👥

PersonaChat comes with 8 pre-loaded characters:

1. **Alex** - Casual Friend (NSFW)
2. **Jordan** - Professional Mentor
3. **Casey** - Creative Enthusiast
4. **Morgan** - Witty Companion (NSFW)
5. **Riley** - Empathetic Listener (NSFW)
6. **Sam** - Adventure Seeker
7. **Avery** - Intellectual Debater
8. **Blake** - Chill Roommate (NSFW)

### Adding New Characters

Edit `server/data/characters.js` to add new characters:

```javascript
{
  id: 9,
  name: 'YourCharacter',
  role: 'Your Role',
  description: 'Character description',
  avatar: 'https://api.dicebear.com/7.x/avataaars/svg?seed=YourCharacter',
  greeting: 'Initial greeting',
  nsfw: false,
  traits: ['Trait1', 'Trait2', 'Trait3'],
  personality: 'Detailed personality description...',
  examples: [
    { user: 'Example user message', response: 'Character response with *actions* and "dialogue"' }
  ]
}
```

## API Endpoints 🔌

### GET `/api/characters`
Returns all available characters

### GET `/api/characters/:id`
Returns a specific character by ID

### GET `/api/characters/search/:query`
Search characters by name, role, or description

### POST `/api/chat`
Send a message and get a character response

**Body:**
```json
{
  "character": { /* character object */ },
  "messages": [ /* conversation history */ ]
}
```

## How It Works 🧠

1. **Character Selection**: Users browse the character grid and click to select
2. **System Prompt**: Each character has a detailed system prompt that guides the AI
3. **Conversation History**: The AI maintains context of the entire conversation
4. **Natural Responses**: The AI generates responses in the character's voice using OpenAI's GPT-4o-mini
5. **Message Formatting**: Responses include actions (*) and dialogue ("") for roleplay

## Customization 🎨

### Styling
- Global styles: `src/index.css`
- Component styles: Individual `.css` files in `src/components/`

### Character Personality
- Modify personality descriptions in `server/data/characters.js`
- Update examples to influence response style
- Adjust system prompt in `server/routes/chat.js`

## Troubleshooting 🔧

**"API key not configured" error**
- Ensure you've added your OpenAI API key to the `.env` file
- Restart the server after updating the `.env` file

**Characters not loading**
- Check that the server is running on port 5000
- Ensure CORS is enabled
- Check browser console for errors

**Slow responses**
- OpenAI API calls can take a few seconds
- Check your internet connection
- Verify API rate limits aren't exceeded

## Performance Tips ⚡

- Use GPU acceleration for smooth animations
- Lazy load character avatars
- Implement message caching for repeated queries
- Consider implementing Redis for session management

## Future Enhancements 🌟

- User authentication and profile system
- Conversation history and favorites
- Custom character creation
- Voice/audio responses
- Multi-language support
- Character collaboration (group chats)
- Advanced emotion detection
- Integration with other AI models

## Contributing 🤝

Contributions are welcome! Please feel free to submit a Pull Request.

## License 📄

This project is open source and available under the MIT License.

## Support 💬

For issues, questions, or suggestions, please create an issue on GitHub.

---

**Made with ❤️ for imagination and AI**
```
