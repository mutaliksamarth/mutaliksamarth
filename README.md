import React, { useState } from 'react';
import { 
  Code, 
  Database, 
  CloudCog, 
  GitBranch, 
  Star, 
  Activity, 
  Linkedin, 
  Twitter, 
  Mail, 
  MousePointerClick 
} from 'lucide-react';

const UltraModernProfile = () => {
  const [activeSection, setActiveSection] = useState(null);

  const technologies = {
    core: [
      { name: 'TypeScript', icon: Code, color: 'from-blue-500 to-indigo-600' },
      { name: 'JavaScript', icon: Code, color: 'from-yellow-400 to-yellow-600' },
      { name: 'Python', icon: Code, color: 'from-green-400 to-emerald-600' },
      { name: 'C++', icon: Code, color: 'from-purple-500 to-indigo-700' }
    ],
    frontend: [
      { name: 'Next.js', icon: CloudCog, color: 'from-gray-800 to-black' },
      { name: 'React', icon: Activity, color: 'from-cyan-400 to-blue-600' },
      { name: 'Tailwind', icon: Star, color: 'from-teal-500 to-emerald-600' }
    ],
    backend: [
      { name: 'Node.js', icon: GitBranch, color: 'from-green-500 to-lime-600' },
      { name: 'Express', icon: Database, color: 'from-gray-600 to-gray-800' },
      { name: 'Prisma', icon: Database, color: 'from-indigo-500 to-purple-600' }
    ]
  };

  const socialLinks = [
    { 
      name: 'LinkedIn', 
      url: 'https://linkedin.com/in/samarth-mutalik02', 
      icon: Linkedin,
      color: 'text-blue-500 hover:text-blue-300'
    },
    { 
      name: 'Twitter', 
      url: 'https://x.com/samarthmutalik2', 
      icon: Twitter,
      color: 'text-sky-500 hover:text-sky-300'
    },
    { 
      name: 'Email', 
      url: 'mailto:mutaliksamarth.02@gmail.com', 
      icon: Mail,
      color: 'text-red-500 hover:text-red-300'
    }
  ];

  return (
    <div className="min-h-screen bg-gradient-to-br from-[#0F172A] via-[#1E293B] to-[#0F172A] text-white overflow-hidden relative">
      {/* Subtle background pattern */}
      <div className="absolute inset-0 opacity-[0.02] bg-[radial-gradient(ellipse_at_center,_var(--tw-gradient-stops))] from-purple-900 via-transparent to-transparent"></div>
      
      <div className="container mx-auto px-4 py-16 relative z-10">
        {/* Hero Section */}
        <div className="text-center mb-16">
          <h1 className="text-5xl font-extrabold mb-4 
            bg-gradient-to-r from-purple-400 via-pink-500 to-indigo-500 
            inline-block text-transparent bg-clip-text">
            Samarth Mutalik
          </h1>
          <p className="text-xl text-gray-300 max-w-2xl mx-auto">
            Crafting digital experiences at the intersection of design, code, and innovation
          </p>
          
          {/* Social Links */}
          <div className="flex justify-center space-x-6 mt-8">
            {socialLinks.map((link) => (
              <a 
                key={link.name}
                href={link.url}
                target="_blank"
                rel="noopener noreferrer"
                className={`
                  ${link.color} 
                  transform transition-all duration-300 
                  hover:-translate-y-2 hover:scale-110
                  p-3 bg-gray-800 rounded-full shadow-lg
                `}
              >
                <link.icon className="w-7 h-7" />
              </a>
            ))}
          </div>
        </div>

        {/* Tech Sections */}
        <div className="grid md:grid-cols-3 gap-8">
          {Object.entries(technologies).map(([category, techs]) => (
            <div 
              key={category}
              className="
                bg-gray-800/50 backdrop-blur-sm 
                border border-gray-700/30 
                rounded-2xl p-6 
                transform transition-all duration-300
                hover:scale-[1.03] hover:shadow-2xl
                hover:border-purple-500/30
              "
              onMouseEnter={() => setActiveSection(category)}
              onMouseLeave={() => setActiveSection(null)}
            >
              <h2 className="text-2xl font-bold mb-6 capitalize text-center">
                {category}
              </h2>
              <div className="space-y-4">
                {techs.map((tech) => (
                  <div 
                    key={tech.name}
                    className="
                      flex items-center space-x-4 
                      bg-gray-700/50 
                      p-3 rounded-xl 
                      transition-all duration-300
                      hover:bg-gray-700/80
                    "
                  >
                    <div className={`
                      bg-gradient-to-br ${tech.color} 
                      p-2 rounded-full 
                      shadow-md
                    `}>
                      <tech.icon className="w-6 h-6 text-white" />
                    </div>
                    <span className="text-gray-200">{tech.name}</span>
                  </div>
                ))}
              </div>
            </div>
          ))}
        </div>

        {/* Interactive CTA */}
        <div className="text-center mt-16">
          <a 
            href="#" 
            className="
              inline-flex items-center space-x-3
              bg-gradient-to-r from-purple-600 to-indigo-600
              px-6 py-3 rounded-full
              text-white font-bold
              hover:from-purple-700 hover:to-indigo-700
              transition-all duration-300
              group
            "
          >
            <span>Let's Collaborate</span>
            <MousePointerClick 
              className="
                w-5 h-5 
                group-hover:animate-bounce
                transition-transform
              " 
            />
          </a>
        </div>
      </div>
    </div>
  );
};

export default UltraModernProfile;
