# Vinh-Com
import { useState } from "react";
import { Card, CardContent } from "@/components/ui/card";
import { Button } from "@/components/ui/button";
import { ShoppingCart } from "lucide-react";

const products = [
  {
    id: 1,
    name: "Crystal Ball - Galaxy",
    price: 499000,
    image: "/images/galaxy.jpg",
  },
  {
    id: 2,
    name: "Crystal Ball - Moon",
    price: 459000,
    image: "/images/moon.jpg",
  },
  {
    id: 3,
    name: "Crystal Ball - Solar System",
    price: 529000,
    image: "/images/solar.jpg",
  },
  {
    id: 4,
    name: "Crystal Ball - Heart",
    price: 399000,
    image: "/images/heart.jpg",
  },
  {
    id: 5,
    name: "Crystal Ball - Unicorn",
    price: 479000,
    image: "/images/unicorn.jpg",
  },
  {
    id: 6,
    name: "Crystal Ball - Deer",
    price: 489000,
    image: "/images/deer.jpg",
  },
  {
    id: 7,
    name: "Crystal Ball - Butterfly",
    price: 419000,
    image: "/images/butterfly.jpg",
  },
  {
    id: 8,
    name: "Crystal Ball - Couple",
    price: 539000,
    image: "/images/couple.jpg",
  },
  {
    id: 9,
    name: "Crystal Ball - Angel",
    price: 499000,
    image: "/images/angel.jpg",
  },
  {
    id: 10,
    name: "Crystal Ball - Tree of Life",
    price: 549000,
    image: "/images/tree.jpg",
  },
];

export default function CrystalBallStore() {
  const [cart, setCart] = useState([]);

  const addToCart = (product) => {
    setCart([...cart, product]);
  };

  return (
    <div className="min-h-screen bg-pink-50 text-gray-800">
      <header className="bg-pink-100 p-4 shadow-md flex justify-between items-center">
        <h1 className="text-2xl font-bold text-pink-600">Crystal Light Store</h1>
        <div className="flex items-center">
          <ShoppingCart className="mr-2" />
          <span>{cart.length}</span>
        </div>
      </header>

      <main className="p-6 grid grid-cols-1 sm:grid-cols-2 md:grid-cols-3 lg:grid-cols-4 gap-6">
        {products.map((product) => (
          <Card key={product.id} className="rounded-2xl shadow-md bg-white">
            <img src={product.image} alt={product.name} className="w-full h-48 object-cover rounded-t-2xl" />
            <CardContent className="p-4">
              <h2 className="text-lg font-semibold text-pink-700">{product.name}</h2>
              <p className="text-md font-medium text-gray-700">{product.price.toLocaleString()} VND</p>
              <Button onClick={() => addToCart(product)} className="mt-2 w-full bg-pink-500 hover:bg-pink-600 text-white">
                Add to Cart
              </Button>
            </CardContent>
          </Card>
        ))}
      </main>

      <footer className="bg-pink-100 p-4 mt-8 text-center text-sm text-gray-600">
        &copy; 2025 Crystal Light Store. All rights reserved.
      </footer>
    </div>
  );
}
