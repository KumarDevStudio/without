# without

import React from 'react';
import Button from './components/Button';

const App = () => {
  const handleClick = () => alert('Button clicked!');

  return <Button label="Click Me" onClick={handleClick} style="primary" />;
};

export default App;


import React from 'react';
import Header from './components/Header';

const App = () => {
  return <Header title="Welcome to the Coding Course App" />;
};

export default App;



import React from 'react';
import Footer from './components/Footer';

const App = () => {
  return <Footer />;
};

export default App;


import React, { useState } from 'react';
import QuizCard from './components/QuizCard';

const quiz = {
  question: 'What is React?',
  options: ['Library', 'Framework', 'Language', 'None of the above'],
};

const App = () => {
  const [selectedAnswer, setSelectedAnswer] = useState('');

  const handleSelect = (option) => setSelectedAnswer(option);

  return (
    <div>
      <QuizCard question={quiz.question} options={quiz.options} onSelect={handleSelect} />
      <p>Selected Answer: {selectedAnswer}</p>
    </div>
  );
};

export default App;

