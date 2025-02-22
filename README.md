import React from 'react';
import { BrowserRouter as Router, Route, Link, Routes } from 'react-router-dom';
import './index.css';

const Home = () => (
  <div className='min-h-screen flex flex-col items-center justify-center bg-pink-100 text-center'>
    <img src='/images/flower-bouquet.jpg' alt='Flower Bouquet' className='w-3/4 md:w-1/2 lg:w-1/3 rounded-2xl shadow-lg mb-8'/>
    <h1 className='text-5xl font-bold text-pink-600'>Happy Birthday, dustu!</h1>
    <p className='text-xl text-gray-700 mt-4'>May your day be as beautiful as this bouquet and as special as you are to me.</p>
    <Link to='/gallery' className='mt-8 px-6 py-3 bg-pink-500 text-white rounded-2xl shadow-lg hover:bg-pink-600'>Memories</Link>
  </div>
);

const Gallery = () => (
  <div className='min-h-screen bg-white p-8'>
    <h2 className='text-4xl font-semibold text-pink-600 text-center mb-6'>Our Memories</h2>
    <div className='grid grid-cols-1 md:grid-cols-2 lg:grid-cols-3 gap-4'>
      {[1, 2, 3, 4, 5, 6].map((i) => (
        <div key={i} className='shadow-lg rounded-2xl overflow-hidden'>
          <img src={`/images/memory${i}.jpg`} alt={`Memory ${i}`} className='w-full h-64 object-cover'/>
          <p className='text-center text-gray-600 p-2'>Beautiful Memory #{i}</p>
        </div>
      ))}
    </div>
    <div className='text-center mt-6'>
      <Link to='/' className='text-pink-500 hover:underline'>Back to Home</Link>
    </div>
  </div>
);

const App = () => (
  <Router>
    <Routes>
      <Route path='/' element={<Home />} />
      <Route path='/gallery' element={<Gallery />} />
    </Routes>
  </Router>
);

export default App;
