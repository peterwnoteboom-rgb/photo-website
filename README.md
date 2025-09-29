// App.jsx
import { motion } from "framer-motion";
import { Card, CardContent } from "@/components/ui/card";
import { Button } from "@/components/ui/button";
import "./App.css";

export default function App() {
  // Replace with your actual GitHub raw image URL
  const photo = {
    src: "[https://raw.githubusercontent.com/your-username/my-portfolio/main/images/mypic.jpg](https://github.com/peterwnoteboom-rgb/photo-website/blob/main/Mountain%20dare%20mighty%20things.jpg)",
    title: "My GitHub Photo"
  };

  return (
    <div className="min-h-screen bg-neutral-50 text-neutral-900">
      {/* Header */}
      <header className="p-6 flex justify-between items-center border-b border-neutral-200">
        <h1 className="text-2xl font-bold">My Photography</h1>
        <nav className="space-x-4">
          <Button variant="ghost">Home</Button>
          <Button variant="ghost">Portfolio</Button>
          <Button variant="ghost">About</Button>
          <Button variant="ghost">Contact</Button>
        </nav>
      </header>

      {/* Hero Section */}
      <section className="relative h-[60vh] flex items-center justify-center bg-black">
        <img
          src={photo.src}
          alt="Hero"
          className="absolute inset-0 w-full h-full object-cover opacity-60"
        />
        <motion.div
          initial={{ opacity: 0, y: 30 }}
          animate={{ opacity: 1, y: 0 }}
          transition={{ duration: 1 }}
          className="relative text-center text-white"
        >
          <h2 className="text-4xl font-bold mb-4">Capturing Moments</h2>
          <p className="mb-6">A portfolio by [Your Name]</p>
          <Button size="lg" className="rounded-2xl">View My Work</Button>
        </motion.div>
      </section>

      {/* Gallery with one image */}
      <section className="p-10 grid grid-cols-1 sm:grid-cols-2 md:grid-cols-3 gap-6">
        <motion.div
          initial={{ opacity: 0, scale: 0.95 }}
          whileInView={{ opacity: 1, scale: 1 }}
          transition={{ duration: 0.5 }}
        >
          <Card className="overflow-hidden rounded-2xl shadow-md">
            <img src={photo.src} alt={photo.title} className="w-full h-64 object-cover" />
            <CardContent className="p-4">
              <h3 className="font-semibold text-lg">{photo.title}</h3>
            </CardContent>
          </Card>
        </motion.div>
      </section>

      {/* Footer */}
      <footer className="p-6 text-center border-t border-neutral-200">
        <p>&copy; {new Date().getFullYear()} [Your Name]. All rights reserved.</p>
      </footer>
    </div>
  );
}
