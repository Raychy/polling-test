# Poll 

This is a simple Vue 3 poll where users can vote for their favorite frontend framework, and results are displayed as percentages with a smooth animation.

## Features
- Display a poll question with four answer options
- Users can vote by clicking an option
- Show vote percentages after voting
- Show total votes

## Technologies Used
- Vue 3 (Composition API)
- TypeScript
- HTML5 
- CSS

## Installation
1. Clone the repository:
   ```sh
   git clone https://github.com/Raychy/polling-test.git
   ```
2. Navigate to the project folder:
   ```sh
   cd polling-test
   ```
3. Install dependencies:
   ```sh
   pnpm install
   ```

## Usage
1. Start the development server:
   ```sh
   pnpm run dev
   ```
2. Open your browser and navigate to `http://localhost:5173/` (or the port specified in your terminal).

## File Structure
```
vue-poll/
│-- src/
│   │-- components/
│   │   ├── Poll.vue  # The main poll component (TypeScript)
│   │-- App.vue       # Root Vue component
│   │-- main.ts       # Entry file (TypeScript)
│-- public/
│-- package.json
│-- README.md
```

## Customization
- Update the `question` variable in `Poll.vue` to change the poll topic.
- Modify the `choices` array to add or remove voting options.
- Adjust CSS styles to fit your design needs.

## Contributing
If you would like to contribute, feel free to fork the repository and submit a pull request!

