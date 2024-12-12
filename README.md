# without


Here's an example implementation for the components structure you shared:


---

1. Button Component

Button.js

import React from 'react';
import './Button.css';

const Button = ({ label, onClick, type = 'button', style = 'primary' }) => {
  return (
    <button className={`button button-${style}`} type={type} onClick={onClick}>
      {label}
    </button>
  );
};

export default Button;

Button.css

.button {
  padding: 10px 20px;
  font-size: 16px;
  border: none;
  border-radius: 5px;
  cursor: pointer;
}

.button-primary {
  background-color: #007bff;
  color: white;
}

.button-secondary {
  background-color: #6c757d;
  color: white;
}

.button-danger {
  background-color: #dc3545;
  color: white;
}

index.js

export { default } from './Button';


---

2. Header Component

Header.js

import React from 'react';
import './Header.css';

const Header = ({ title }) => {
  return (
    <header className="header">
      <h1>{title}</h1>
    </header>
  );
};

export default Header;

Header.css

.header {
  background-color: #343a40;
  color: white;
  padding: 10px 20px;
  text-align: center;
}

.header h1 {
  margin: 0;
  font-size: 24px;
}

index.js

export { default } from './Header';


---

3. Footer Component

Footer.js

import React from 'react';
import './Footer.css';

const Footer = () => {
  return (
    <footer className="footer">
      <p>&copy; 2024 Coding Course App. All Rights Reserved.</p>
    </footer>
  );
};

export default Footer;

Footer.css

.footer {
  background-color: #f8f9fa;
  color: #6c757d;
  padding: 10px 20px;
  text-align: center;
  position: fixed;
  bottom: 0;
  width: 100%;
}

.footer p {
  margin: 0;
  font-size: 14px;
}

index.js

export { default } from './Footer';


---

4. QuizCard Component

QuizCard.js

import React from 'react';
import './QuizCard.css';

const QuizCard = ({ question, options, onSelect }) => {
  return (
    <div className="quiz-card">
      <h3>{question}</h3>
      <div className="quiz-options">
        {options.map((option, index) => (
          <label key={index} className="quiz-option">
            <input
              type="radio"
              name="quiz"
              value={option}
              onClick={() => onSelect(option)}
            />
            {option}
          </label>
        ))}
      </div>
    </div>
  );
};

export default QuizCard;

QuizCard.css

.quiz-card {
  border: 1px solid #ddd;
  border-radius: 5px;
  padding: 15px;
  margin-bottom: 15px;
  background-color: #fff;
}

.quiz-card h3 {
  font-size: 18px;
  margin-bottom: 10px;
}

.quiz-options {
  display: flex;
  flex-direction: column;
}

.quiz-option {
  margin-bottom: 8px;
  font-size: 16px;
}

.quiz-option input {
  margin-right: 10px;
}

index.js

export { default } from './QuizCard';


---

Usage Examples

Button Component

import React from 'react';
import Button from './components/Button';

const App = () => {
  const handleClick = () => alert('Button clicked!');

  return <Button label="Click Me" onClick={handleClick} style="primary" />;
};

export default App;

Header Component

import React from 'react';
import Header from './components/Header';

const App = () => {
  return <Header title="Welcome to the Coding Course App" />;
};

export default App;

Footer Component

import React from 'react';
import Footer from './components/Footer';

const App = () => {
  return <Footer />;
};

export default App;

QuizCard Component

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

This structure ensures modular, reusable, and easy-to-maintain components for your application. Let me know if you'd like to expand this further!

