import styles from 'app/page.module.css'
import Image from 'next/image'
import React from 'react';
import Link from 'next/link';

export const metadata = {
    title: 'Sketches',
    description: '-',
  }


const data = [
  {
    image: '/images/sketches/sketch test scan website2.png',
  },
  {
  image: '/images/sketches/sketch test scan website.png',
  },
  {
  image: '/images/sketches/sketch test scan website3.png',
  },
  {
  image: '/images/sketches/sketch test scan website4.png',
  },
  {
  image: '/images/sketches/sketch test scan website5.png',
  },
];

const data2 = [
  {
    image: '/images/sketches/metal2.png',
  },
  {
    image: '/images/sketches/cat3.png',
  },
  {
    image: '/images/sketches/dragon2.png',
  },
  {
  image: '/images/sketches/illusions2.png',
  },
];

const data3 = [
{ image: '/images/sketches/cartoon2.png' },
{ image: '/images/sketches/corona memory3.png' },
{ image: '/images/sketches/spaceship sketch2.png' },
]

export default function sketches() {
    return (
        <main className={styles.main}>
              <div className="relative 
   flex 
   place-items-center 
   before:absolute 
   before:h-[300px] 
   before:w-[480px] 
   before:-translate-x-1/2 
   before:rounded-full 
   before:bg-gradient-radial 
   before:from-white 
   before:to-transparent 
   before:blur-2xl 
   before:content-[''] 
   after:absolute 
   after:-z-20 
   after:h-[180px] 
   after:w-[240px] 
   after:translate-x-1/3 
   after:bg-gradient-conic 
   after:from-sky-200 
   after:via-blue-200 
   after:blur-2xl 
   after:content-[''] 
   before:dark:bg-gradient-to-br 
   before:dark:from-transparent 
   before:dark:to-blue-700 
   before:dark:opacity-10 
   after:dark:from-sky-900 
   after:dark:via-[#0141ff] 
   after:dark:opacity-40 
   before:lg:h-[360px] 
   z-[-1]">
          </div>
      
            <h1 className={styles.title}>
             Sketches
            </h1>

            {/* <div className={styles.container}>
              <div className={styles.header}>
                <h1 className={styles.title}> Sketches </h1>
                  <div className={styles.backbutton}> 
                    <h1> <Link href="/projects"> Back to Projects </Link> </h1> 
                </div> 
              </div>              
            </div> */}

            <div className={styles.subtitledescription}>
            <p>
            A collection of sketches, designs and artworks ranging from 2018 
            to 2023.   
             </p>
            </div>

            <div className="">
              <div className="p-3 container mx-auto">
                <div className="py-2">
                </div>

 {/* for media resizing */}

                  <div className="md:flex md:gap-2 md:grid-cols-2 lg:grid-cols-3 mb-2">
                    {data.map((x) => {
                      return (
                        <>
                 
                  <article
                    className="p-3 mb-6  transition duration-300 group transform hover:-translate-y-2 hover:shadow-2xl rounded-2xl cursor-pointer"
                  >
                    <div className="relative mb-4 rounded-2xl">
                      <Image
                        width={400}
                        height={400}
                        className="max-h-80 rounded-2xl w-full object-cover transition-transform duration-300 transform group-hover:scale-105"
                        src={x.image}
                        alt=""
                      />
                    </div>
                  </article>
                  
                  </>
                    );
                  })}
                </div>
              </div>
            </div>
            
            <div className="">
              <div className="p-3 container mx-auto">
                <div className="py-2">
                </div>
                  <div className="md:flex md:gap-2 md:grid-cols-2 lg:grid-cols-3 mb-12">
                    {data2.map((x) => {
                      return (
                        <>
                 
                  <article
                    className="p-3 mb-6  transition duration-300 group transform hover:-translate-y-2 hover:shadow-2xl rounded-2xl cursor-pointer"
                  >
                    <div className="relative mb-4 rounded-2xl">
                      <Image
                        width={400}
                        height={400}
                        className="max-h-80 rounded-2xl w-full object-cover transition-transform duration-300 transform group-hover:scale-105"
                        src={x.image}
                        alt=""
                      />
                    </div>
                  </article>
                  
                  </>
                    );
                  })}
                </div>
              </div>
            </div>

            <div className="">
              <div className="p-3 container mx-auto">
                <div className="py-2">
                </div>
                  <div className="md:flex md:gap-2 md:grid-cols-2 lg:grid-cols-3 mb-12">
                    {data3.map((x) => {
                      return (
                        <>
                 
                  <article
                    className="p-3 mb-6  transition duration-300 group transform hover:-translate-y-2 hover:shadow-2xl rounded-2xl cursor-pointer"
                  >
                    <div className="relative mb-4 rounded-2xl">
                      <Image
                        width={400}
                        height={400}
                        className="max-h-80 rounded-2xl w-full object-cover transition-transform duration-300 transform group-hover:scale-105"
                        src={x.image}
                        alt=""
                      />
                    </div>
                  </article>
                  
                  </>
                    );
                  })}
                </div>
              </div>
            </div>

   
        </main>
    )
}






sketch page with next/prev image:

'use client'
import styles from 'app/page.module.css'
import Image from 'next/image'
import React, {useState, useEffect} from 'react';
import Link from 'next/link';
import { IoIosArrowBack, IoIosArrowForward } from "react-icons/io";
import { PiXCircle } from "react-icons/pi"; 




const data = [
  {
    image: '/images/sketches/sketch test scan website2.png', id: 0,
  },
  {
  image: '/images/sketches/sketch test scan website.png', id: 1,
  },
  {
  image: '/images/sketches/sketch test scan website3.png' , id: 2,
  },
  {
  image: '/images/sketches/sketch test scan website4.png' , id: 3,
  },
  {
  image: '/images/sketches/sketch test scan website5.png' , id: 4,
  },

  /*breakpoint*/

  {
    image: '/images/sketches/metal2.png' , id: 5,
  },
  {
    image: '/images/sketches/cat3.png' , id: 6,
  },
  {
    image: '/images/sketches/dragon2.png' , id: 7,
  },
  {
  image: '/images/sketches/illusions2.png' , id: 8,
  },

/*breakpoint*/

{ image: '/images/sketches/cartoon2.png', id: 9 },
{ image: '/images/sketches/corona memory3.png', id: 10 },
{ image: '/images/sketches/spaceship sketch2.png', id: 11 },
]

export default function sketches() {

  const [selectedImage, setSelectedImage] = useState(null);
  const [currentIndex, setCurrentIndex] = useState(0);

  const handleImageClick = (imageSrc) => {
    setSelectedImage(imageSrc);
  };

const handleResetClick = () => {
    setSelectedImage(null);
};

const handlePrevClick = () => {
    setCurrentIndex((prevIndex) => (prevIndex === 0 ? data.length - 1 : prevIndex - 1));
    setSelectedImage(data[currentIndex === 0 ? data.length - 1 : currentIndex - 1].image);
  };

const handleNextClick = () => {
    setCurrentIndex((prevIndex) => (prevIndex === data.length - 1 ? 0 : prevIndex + 1));
    setSelectedImage(data[currentIndex === data.length - 1 ? 0 : currentIndex + 1].image);
  };


  useEffect(() => {
    document.title = 'Sketches';
  }, []);

  useEffect(() => {
    const handleKeyDown = (event) => {
    if (event.key === 'Escape') {
        handleResetClick();
    } else if (event.key === 'ArrowLeft') {
      handleNextClick();
    } else if (event.key === 'ArrowRight') {
      handlePrevClick();
    }
  };

  
  window.addEventListener('keydown', handleKeyDown);

  return () => {
    window.removeEventListener('keydown', handleKeyDown);
  };
}, []);

  return (

        <main className={styles.main}>
              <div className="relative 
   flex 
   place-items-center 
   before:absolute 
   before:h-[300px] 
   before:w-[480px] 
   before:-translate-x-1/2 
   before:rounded-full 
   before:bg-gradient-radial 
   before:from-white 
   before:to-transparent 
   before:blur-2xl 
   before:content-[''] 
   after:absolute 
   after:-z-20 
   after:h-[180px] 
   after:w-[240px] 
   after:translate-x-1/3 
   after:bg-gradient-conic 
   after:from-sky-200 
   after:via-blue-200 
   after:blur-2xl 
   after:content-[''] 
   before:dark:bg-gradient-to-br 
   before:dark:from-transparent 
   before:dark:to-blue-700 
   before:dark:opacity-10 
   after:dark:from-sky-900 
   after:dark:via-[#0141ff] 
   after:dark:opacity-40 
   before:lg:h-[360px] 
   z-[-1]">
          </div>
      
            <h1 className={styles.title}>
             Sketches
            </h1>

            {/* <div className={styles.container}>
              <div className={styles.header}>
                <h1 className={styles.title}> Sketches </h1>
                  <div className={styles.backbutton}> 
                    <h1> <Link href="/projects"> Back to Projects </Link> </h1> 
                </div> 
              </div>              
            </div> */}

            <div className={styles.subtitledescription}>
            <p>
            A collection of sketches, designs and artworks ranging from 2018 
            to 2023.   
             </p>
            </div>
            
            <div className="">
            {selectedImage && (
        <div id="overlay" className="fixed top-0 left-0 right-0 bottom-0 flex items-center justify-center bg-black bg-opacity-75  z-50">
          <img
            src={selectedImage}
            alt=""
            className="max-w-full max-h-full"
            style={{ maxHeight: '80vh', zIndex: 9990 }}
          />
           <button
            className="absolute top-20 right-5 bg-white text-black shadow-lg bg-opacity-50 px-2 py-1 rounded"
            onClick={handleResetClick}
            style={{ zIndex: 9999 }}
          >
            <PiXCircle style={{ fontSize: '2rem' }} />
          </button>
          <div className='absolute left-5 bg-white text-black shadow-lg bg-opacity-50 px-2 py-1 rounded'>
            <button
              className= "text-black px-0 py-4 rounded-r"
              onClick={handlePrevClick}
              style={{ zIndex: 9999 }}
            >
              <IoIosArrowBack style={{ fontSize: '2rem' }}/>
            </button>
            </div>
            {/* <div className="absolute right-5"> */}
            <div className= 'absolute right-5 bg-white text-black shadow-lg bg-opacity-50 px-2 py-1 rounded'>
            <button
              className=" text-black px-0 py-4 rounded-r"
              onClick={handleNextClick}
              style={{ zIndex: 9999 }}
            >
              <IoIosArrowForward style={{ fontSize: '2rem' }}/>
            </button>
          </div>
        </div>
        
      )}
              <div className="p-3 container mx-auto">
                <div className="py-2"></div>
                  <div className="md:flex md:gap-2 md:grid-cols-5 lg:grid-cols-3 mb-12" style={{ flexWrap: 'wrap', justifyContent: 'center' }}>
                    {data.map((x, index) =>  (
                        <React.Fragment key={x.id}>
                  <article
                  key={x.id}
                    className="p-3 mb-6  transition duration-300 group transform hover:-translate-y-2 hover:shadow-2xl rounded-2xl cursor-pointer"
                    style={{ marginBottom: index === 4 || index === 8 ? '1rem' : '0' }}
                  >
                    <div className="relative mb-4 rounded-2xl">
                      <Image
                        width={400}
                        height={400}
                        className={`max-h-80 rounded-2xl w-full object-cover transition-transform duration-300 transform group-hover:scale-105 ${
                          selectedImage ? 'z-0' : ''
                        }`}
                        src={x.image}
                        alt=""
                        onClick={() => handleImageClick(x.image)}
                      />
                    </div>
                  </article>
               
                  </React.Fragment>
                    ))}
                  </div>
                </div>
              </div>

   
        </main>
    )
}


