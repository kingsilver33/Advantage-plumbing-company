# Advantage-plumbing-company
{
  "name": "advantage-plumbing",
  "version": "1.0.0",
  "private": true,
  "scripts": {
    "dev": "next dev",
    "build": "next build",
    "start": "next start"
  },
  "dependencies": {
    "next": "14.2.5",
    "react": "18.2.0",
    "react-dom": "18.2.0",
    "lucide-react": "^0.408.0",
    "framer-motion": "^11.3.21"
  },
  "devDependencies": {
    "tailwindcss": "^3.4.7",
    "postcss": "^8.4.39",
    "autoprefixer": "^10.4.19"
  }
}
/** @type {import('next').NextConfig} */
const nextConfig = {
  reactStrictMode: true
};

module.exports = nextConfig;
module.exports = {
  content: [
    "./app/**/*.{js,jsx}",
    "./components/**/*.{js,jsx}"
  ],
  theme: {
    extend: {}
  },
  plugins: []
};
module.exports = {
  plugins: {
    tailwindcss: {},
    autoprefixer: {}
  }
};
@tailwind base;
@tailwind components;
@tailwind utilities;

html, body {
  padding: 0;
  margin: 0;
}
import "./globals.css";

export const metadata = {
  title: "Advantage Plumbing",
  description: "Professional Plumbing Services"
};

export default function RootLayout({ children }) {
  return (
    <html lang="en">
      <body>{children}</body>
    </html>
  );
}
import { Phone, MapPin, Droplet, Flame, Wrench, ShieldCheck } from "lucide-react";
import { motion } from "framer-motion";

export default function Home() {
  return (
    <div className="min-h-screen bg-slate-50 text-slate-800">
      {/* Hero */}
      <header className="bg-blue-900 text-white">
        <div className="max-w-6xl mx-auto px-6 py-16 grid md:grid-cols-2 gap-8 items-center">
          <motion.div initial={{ opacity: 0, y: 20 }} animate={{ opacity: 1, y: 0 }}>
            <h1 className="text-4xl md:text-5xl font-bold mb-4">
              ADVANTAGE PLUMBING
            </h1>
            <p className="text-lg mb-6">
              Reliable • Honest • Professional Plumbing Services
            </p>
            <a
              href="tel:8063958270"
              className="inline-block bg-white text-blue-900 px-6 py-3 rounded-xl font-semibold"
            >
              Call Now
            </a>
          </motion.div>

          <div className="space-y-3 text-lg">
            <p className="flex items-center gap-2">
              <Phone /> 806-395-8270
            </p>
            <p className="flex items-center gap-2">
              <MapPin /> 618 N Florida St
            </p>
          </div>
        </div>
      </header>

      {/* Services */}
      <section className="max-w-6xl mx-auto px-6 py-16">
        <h2 className="text-3xl font-bold text-center mb-12">Our Services</h2>
        <div className="grid md:grid-cols-3 gap-6">
          <Service icon={<Droplet size={36} />} title="Residential Plumbing" />
          <Service icon={<Flame size={36} />} title="Gas Lines" />
          <Service icon={<Wrench size={36} />} title="Drain & Sewer" />
        </div>
      </section>

      {/* Why Us */}
      <section className="bg-white py-16">
        <div className="max-w-6xl mx-auto px-6">
          <h2 className="text-3xl font-bold text-center mb-12">
            Why Choose Advantage Plumbing
          </h2>
          <div className="grid md:grid-cols-3 gap-6">
            <Feature icon={<ShieldCheck size={36} />} title="Licensed & Insured" />
            <Feature icon={<Wrench size={36} />} title="Experienced Work" />
            <Feature icon={<Phone size={36} />} title="Fast Response" />
          </div>
        </div>
      </section>

      {/* Contact */}
      <section className="max-w-6xl mx-auto px-6 py-16 text-center">
        <h2 className="text-3xl font-bold mb-6">Contact Us</h2>
        <p className="text-lg">📞 806-395-8270</p>
        <p className="text-lg">📍 618 N Florida St</p>
      </section>

      {/* Footer */}
      <footer className="bg-blue-900 text-white text-center py-6">
        © {new Date().getFullYear()} Advantage Plumbing
      </footer>
    </div>
  );
}

function Service({ icon, title }) {
  return (
    <div className="bg-white rounded-2xl shadow p-6 text-center">
      <div className="mb-4 flex justify-center">{icon}</div>
      <h3 className="text-xl font-semibold">{title}</h3>
    </div>
  );
}

function Feature({ icon, title }) {
  return (
    <div className="bg-white rounded-2xl shadow p-6 text-center">
      <div className="mb-4 flex justify-center">{icon}</div>
      <h3 className="text-xl font-semibold">{title}</h3>
    </div>
  );
}
# Advantage Plumbing

Professional plumbing website deployed on Vercel.
