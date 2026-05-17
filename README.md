# due-date-coffee
import { createFileRoute } from "@tanstack/react-router";
import hero from "@/assets/hero.jpg";
import craft from "@/assets/craft.jpg";
import icedv60 from "@/assets/icedv60.jpg";
import cheesecake from "@/assets/cheesecake.jpg";
import flatwhite from "@/assets/flatwhite.jpg";
import matcha from "@/assets/matcha.jpg";
import tiramisu from "@/assets/tiramisu.jpg";
import affogato from "@/assets/affogato.jpg";

export const Route = createFileRoute("/")({
  component: Index,
  head: () => ({
    meta: [
      { title: "DUE DATE — Specialty Coffee in Al Khobar" },
      { name: "description", content: "Specialty coffee, signature desserts, and a calm atmosphere in Al Khobar. Coffee worth slowing down for." },
      { property: "og:title", content: "DUE DATE — Coffee worth slowing down for" },
      { property: "og:description", content: "Specialty coffee, signature desserts, and a calm atmosphere in Al Khobar." },
      { property: "og:type", content: "restaurant" },
      { property: "og:image", content: hero },
      { name: "twitter:card", content: "summary_large_image" },
      { name: "twitter:image", content: hero },
    ],
    links: [
      { rel: "canonical", href: "/" },
      { rel: "preconnect", href: "https://fonts.googleapis.com" },
      { rel: "preconnect", href: "https://fonts.gstatic.com", crossOrigin: "" },
      { rel: "stylesheet", href: "https://fonts.googleapis.com/css2?family=Cormorant+Garamond:ital,wght@0,400;0,500;0,600;1,400;1,600&family=Inter:wght@300;400;500&family=JetBrains+Mono:wght@400&display=swap" },
    ],
    scripts: [{
      type: "application/ld+json",
      children: JSON.stringify({
        "@context": "https://schema.org",
        "@type": "CafeOrCoffeeShop",
        name: "DUE DATE",
        description: "Specialty coffee, signature desserts, and a calm atmosphere designed for deep conversations and slow evenings.",
        address: { "@type": "PostalAddress", streetAddress: "9633+HF2, Al Rakah Al Janubiyah", addressLocality: "Al Khobar", postalCode: "34226", addressCountry: "SA" },
        telephone: "+966 50 758 1815",
        image: hero,
        servesCuisine: "Coffee, Desserts",
      }),
    }],
  }),
});

const favorites = [
  { name: "Iced V60", notes: "Bright · Fruity · Smooth", img: icedv60 },
  { name: "Espresso Cheesecake", notes: "Rich · Soft · Signature", img: cheesecake },
  { name: "Flat White", notes: "Velvety · Balanced · Classic", img: flatwhite },
  { name: "Matcha Latte", notes: "Creamy · Sweet · Clean", img: matcha },
  { name: "Tiramisu", notes: "Soft · Rich · Traditional", img: tiramisu },
  { name: "Affogato", notes: "Bold · Cold · Contrast", img: affogato },
];

const testimonials = [
  "The place is calm, beautiful, and psychologically comfortable. The coffee and desserts are genuinely memorable.",
  "The espresso cheesecake alone is enough to make me come back again and again.",
  "One of the quietest and most relaxing cafés — with classy service and amazing coffee.",
  "The details stand out. The writing on the cups, the packaging, the atmosphere — everything feels intentional.",
];

function Index() {
  return (
    <div className="bg-background text-foreground font-sans selection:bg-accent/30">
      {/* Nav */}
      <nav className="fixed top-0 z-50 flex w-full items-center justify-between px-6 py-7 md:px-12 mix-blend-difference text-cream">
        <a href="#top" className="font-display text-2xl italic tracking-tight">Due Date</a>
        <div className="hidden md:flex gap-10 font-mono text-[10px] uppercase tracking-[0.25em]">
          <a href="#menu" className="hover:opacity-60 transition-opacity">Menu</a>
          <a href="#story" className="hover:opacity-60 transition-opacity">Story</a>
          <a href="#visit" className="hover:opacity-60 transition-opacity">Visit</a>
        </div>
        <a href="tel:+966507581815" className="hidden md:block font-mono text-[10px] uppercase tracking-[0.25em] hover:opacity-60 transition-opacity">
          +966 50 758 1815
        </a>
      </nav>

      {/* Hero */}
      <section id="top" className="relative h-screen min-h-[680px] w-full overflow-hidden">
        <div className="absolute inset-0">
          <img src={hero} alt="Steaming pour-over coffee in a warm Al Khobar café at golden hour" width={1920} height={1080} className="h-full w-full object-cover slow-zoom" />
          <div className="absolute inset-0 bg-gradient-to-b from-espresso/30 via-espresso/10 to-background" />
          <div className="absolute inset-0 bg-gradient-to-t from-espresso/60 via-transparent to-espresso/40" />
        </div>
        <div className="relative z-10 flex h-full flex-col items-center justify-center px-6 text-center text-cream">
          <span className="reveal font-mono text-[10px] uppercase tracking-[0.4em] opacity-80">Al Khobar — Saudi Arabia</span>
          <h1 className="reveal-200 font-display italic leading-[0.9] tracking-tight mt-6 text-7xl sm:text-8xl md:text-[12rem]">Due Date</h1>
          <p className="reveal-400 font-mono text-[11px] uppercase tracking-[0.4em] mt-8 opacity-90">Coffee worth slowing down for</p>
          <div className="reveal-600 mt-14 flex flex-col sm:flex-row gap-4">
            <a href="#menu" className="group inline-flex items-center justify-center gap-3 bg-cream text-espresso px-8 py-4 font-mono text-[10px] uppercase tracking-[0.25em] hover:bg-amber transition-colors">
              Explore the Menu
              <span className="transition-transform group-hover:translate-x-1">→</span>
            </a>
            <a href="#visit" className="inline-flex items-center justify-center gap-3 border border-cream/40 text-cream px-8 py-4 font-mono text-[10px] uppercase tracking-[0.25em] hover:bg-cream/10 transition-colors">
              Find Us
            </a>
          </div>
        </div>
        <div className="absolute bottom-10 left-1/2 -translate-x-1/2 flex flex-col items-center gap-3 text-cream/70">
          <span className="font-mono text-[9px] uppercase tracking-[0.4em] italic">Scroll to exhale</span>
          <div className="h-12 w-px bg-gradient-to-b from-cream/60 to-transparent" />
        </div>
      </section>

      {/* Story */}
      <section id="story" className="mx-auto grid max-w-screen-xl grid-cols-1 items-center gap-16 px-6 py-32 md:grid-cols-12 md:px-12 md:py-40">
        <div className="md:col-span-5 space-y-8">
          <span className="font-mono text-[10px] uppercase tracking-[0.3em] text-amber">The Story</span>
          <h2 className="font-display text-5xl md:text-6xl leading-[1.05] text-balance">
            Designed for <br /><span className="italic">slow moments.</span>
          </h2>
          <p className="text-lg leading-relaxed text-muted-foreground text-pretty max-w-[44ch]">
            DUE DATE was created for people who appreciate simplicity done well. From carefully selected beans to handcrafted desserts and calming interiors, every detail is built around comfort, quality, and atmosphere.
          </p>
          <p className="text-base leading-relaxed text-muted-foreground text-pretty max-w-[44ch]">
            Whether you're meeting friends, working quietly, or escaping the noise of the city, the café offers a space that feels warm, personal, and intentional.
          </p>
        </div>
        <div className="md:col-span-7 md:pl-12">
          <div className="relative">
            <img src={craft} alt="Barista pouring a pour-over coffee with care" width={1024} height={1024} loading="lazy" className="w-full aspect-[4/5] object-cover" />
            <div className="absolute -bottom-6 -left-6 hidden md:block bg-cream px-6 py-5 max-w-[18rem] border border-border">
              <p className="font-display italic text-lg leading-snug">"Coffee, quietly perfected."</p>
            </div>
          </div>
        </div>
      </section>

      {/* Menu */}
      <section id="menu" className="bg-paper py-32 md:py-40">
        <div className="mx-auto max-w-screen-xl px-6 md:px-12">
          <div className="mb-20 flex flex-col items-start justify-between gap-8 md:flex-row md:items-end">
            <div className="space-y-4">
              <span className="font-mono text-[10px] uppercase tracking-[0.3em] text-amber">Signature Favorites</span>
              <h2 className="font-display text-5xl md:text-7xl italic leading-[0.95]">
                A hidden favorite <br /> for coffee lovers.
              </h2>
            </div>
            <p className="max-w-[34ch] font-mono text-[10px] uppercase tracking-[0.2em] text-muted-foreground md:text-right">
              Crafted daily with precision, balance, and seasonal beans.
            </p>
          </div>
          <div className="grid grid-cols-1 gap-x-10 gap-y-20 md:grid-cols-2 lg:grid-cols-3">
            {favorites.map((item, i) => (
              <article key={item.name} className={`group ${i % 3 === 1 ? "lg:translate-y-16" : ""}`}>
                <div className="overflow-hidden">
                  <img src={item.img} alt={item.name} width={800} height={1024} loading="lazy" className="w-full aspect-[4/5] object-cover transition-transform duration-[1200ms] group-hover:scale-105" />
                </div>
                <div className="mt-6 flex items-start justify-between gap-6">
                  <div>
                    <h3 className="font-display text-2xl italic">{item.name}</h3>
                    <p className="mt-1 font-mono text-[10px] uppercase tracking-[0.2em] text-muted-foreground">{item.notes}</p>
                  </div>
                  <span className="font-mono text-[10px] uppercase tracking-[0.2em] text-muted-foreground pt-2">0{i + 1}</span>
                </div>
              </article>
            ))}
          </div>
          <div className="mt-24 grid grid-cols-2 md:grid-cols-4 gap-6 border-t border-border pt-12 text-sm">
            {["Croissants", "Danish Pastries", "Hot Chocolate + Espresso", "Pour-Over Selection"].map((n) => (
              <div key={n} className="font-display italic text-2xl md:text-3xl">{n}.</div>
            ))}
          </div>
        </div>
      </section>

      {/* Experience pillars */}
      <section className="mx-auto max-w-screen-xl px-6 md:px-12 py-32 md:py-40">
        <span className="font-mono text-[10px] uppercase tracking-[0.3em] text-amber">The Experience</span>
        <h2 className="font-display text-5xl md:text-6xl italic mt-4 max-w-[18ch] leading-[1.05]">More than coffee.</h2>
        <div className="mt-20 grid grid-cols-1 md:grid-cols-3 gap-12">
          {[
            { t: "Quiet Atmosphere", d: "A calm space ideal for studying, working, reading, or slow conversations." },
            { t: "Specialty Coffee", d: "Balanced brews crafted with precision, made from carefully selected beans." },
            { t: "Thoughtful Details", d: "Handwritten cup messages, premium packaging, and warm, elegant hospitality." },
          ].map((p) => (
            <div key={p.t} className="border-l border-border pl-8 space-y-4">
              <h3 className="font-display text-3xl italic">{p.t}</h3>
              <p className="text-muted-foreground leading-relaxed text-pretty">{p.d}</p>
            </div>
          ))}
        </div>
      </section>

      {/* Testimonials */}
      <section className="bg-espresso text-cream py-32 md:py-40 overflow-hidden">
        <div className="mx-auto max-w-screen-xl px-6 md:px-12">
          <span className="font-mono text-[10px] uppercase tracking-[0.3em] text-amber">Voices</span>
          <h2 className="font-display text-5xl md:text-6xl italic mt-4 mb-20 max-w-[20ch] leading-[1.05]">What people are saying.</h2>
          <div className="grid grid-cols-1 md:grid-cols-2 gap-x-16 gap-y-20">
            {testimonials.map((q, i) => (
              <figure key={i} className="space-y-6">
                <p className="font-display text-2xl md:text-3xl italic leading-snug text-balance">&ldquo;{q}&rdquo;</p>
                <figcaption className="flex items-center gap-4 font-mono text-[10px] uppercase tracking-[0.3em] text-cream/50">
                  <span className="h-px w-8 bg-cream/30" />
                  Guest, Al Khobar
                </figcaption>
              </figure>
            ))}
          </div>
        </div>
      </section>

      {/* Visit */}
      <section id="visit" className="bg-paper py-32 md:py-40">
        <div className="mx-auto max-w-screen-xl px-6 md:px-12 grid grid-cols-1 md:grid-cols-12 gap-16">
          <div className="md:col-span-7 space-y-12">
            <div>
              <span className="font-mono text-[10px] uppercase tracking-[0.3em] text-amber">Visit</span>
              <h2 className="font-display text-6xl md:text-8xl italic leading-[0.95] mt-4">
                Slow coffee. <br /> Warm light. <br /> Good company.
              </h2>
            </div>
            <div className="grid grid-cols-1 sm:grid-cols-2 gap-10 max-w-xl">
              <div className="space-y-2">
                <p className="font-mono text-[10px] uppercase tracking-[0.3em] text-amber">Location</p>
                <p className="text-base leading-relaxed">
                  9633+HF2, Al Rakah Al Janubiyah<br />Al Khobar 34226<br />Saudi Arabia
                </p>
              </div>
              <div className="space-y-2">
                <p className="font-mono text-[10px] uppercase tracking-[0.3em] text-amber">Contact</p>
                <a href="tel:+966507581815" className="block text-base hover:text-amber transition-colors">+966 50 758 1815</a>
                <p className="font-mono text-[10px] uppercase tracking-[0.2em] text-muted-foreground pt-4">
                  Open Daily · Mornings to Late Evenings
                </p>
              </div>
            </div>
            <div className="flex flex-wrap gap-4">
              <a href="https://www.google.com/maps/search/?api=1&query=9633%2BHF2+Al+Rakah+Al+Janubiyah+Al+Khobar" target="_blank" rel="noreferrer noopener" className="group inline-flex items-center gap-3 bg-espresso text-cream px-8 py-4 font-mono text-[10px] uppercase tracking-[0.25em] hover:bg-amber hover:text-espresso transition-colors">
                Get Directions
                <span className="transition-transform group-hover:translate-x-1">→</span>
              </a>
              <a href="tel:+966507581815" className="inline-flex items-center gap-3 border border-espresso/30 px-8 py-4 font-mono text-[10px] uppercase tracking-[0.25em] hover:bg-espresso hover:text-cream transition-colors">
                Call the Café
              </a>
            </div>
          </div>
          <div className="md:col-span-5">
            <div className="aspect-[4/5] w-full overflow-hidden border border-border">
              <iframe title="DUE DATE location map" src="https://www.google.com/maps?q=9633%2BHF2+Al+Rakah+Al+Janubiyah+Al+Khobar&output=embed" className="h-full w-full grayscale" loading="lazy" referrerPolicy="no-referrer-when-downgrade" />
            </div>
          </div>
        </div>
      </section>

      {/* Footer */}
      <footer className="bg-espresso text-cream py-16">
        <div className="mx-auto max-w-screen-xl px-6 md:px-12 flex flex-col md:flex-row items-start md:items-center justify-between gap-8">
          <div className="space-y-3">
            <p className="font-display text-3xl italic">Due Date</p>
            <p className="font-mono text-[10px] uppercase tracking-[0.3em] opacity-50">
              Specialty coffee · Signature desserts · Calm atmosphere
            </p>
          </div>
          <p className="font-mono text-[10px] uppercase tracking-[0.3em] opacity-40">
            © {new Date().getFullYear()} Due Date — Coffee, quietly perfected.
          </p>
        </div>
      </footer>

      {/* Mobile sticky CTA */}
      <a href="tel:+966507581815" className="fixed bottom-5 left-1/2 -translate-x-1/2 z-50 md:hidden w-[calc(100%-2.5rem)] max-w-sm bg-espresso text-cream py-4 text-center font-mono text-[10px] uppercase tracking-[0.3em] shadow-2xl ring-1 ring-cream/10">
        Call · +966 50 758 1815
      </a>
    </div>
  );
}