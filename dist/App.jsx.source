import React, { useState, useEffect } from 'react';
import { Zap, ArrowRight, MessageSquare, DollarSign, Check, Star } from 'lucide-react';

function useAuth() {
  const [user, setUser] = useState(null);
  const login = (userData) => setUser(userData);
  const logout = () => setUser(null);
  const signup = (userData) => setUser(userData);
  return { user, login, logout, signup };
}

function LandingPage({ onGetStarted, onSignup, onLogin }) {
  const [name, setName] = useState('');
  const [email, setEmail] = useState('');
  const [password, setPassword] = useState('');
  const [error, setError] = useState('');
  const [showLogin, setShowLogin] = useState(false);
  const [loginEmail, setLoginEmail] = useState('');
  const [loginPassword, setLoginPassword] = useState('');

  const handleSignup = (e) => {
    e.preventDefault();
    if (!name || !email || !password) {
      setError('All fields required');
      return;
    }
    if (password.length < 6) {
      setError('Password must be at least 6 characters');
      return;
    }
    setError('');
    onSignup({ name, email, plan: 'free', joinedAt: Date.now() });
  };

  const handleLogin = (e) => {
    e.preventDefault();
    if (!loginEmail || !loginPassword) {
      setError('Email and password required');
      return;
    }
    setError('');
    onLogin({ name: loginEmail.split('@')[0], email: loginEmail, plan: 'free', joinedAt: Date.now() });
  };

  return (
    <div className="min-h-screen bg-[#06080f] text-slate-100 font-['Inter']">
      {/* Navigation */}
      <nav className="flex items-center justify-between px-8 py-4 border-b border-white/5">
        <div className="flex items-center gap-3">
          <div className="w-8 h-8 bg-gradient-to-br from-[#F7931E] to-[#1E3A5F] rounded-lg flex items-center justify-center">
            <Zap className="w-5 h-5 text-white" />
          </div>
          <span className="font-semibold text-lg">InvoiceHero</span>
        </div>
        <div className="flex items-center gap-4">
          <button onClick={() => setShowLogin(true)} className="text-slate-300 hover:text-white transition-colors">Sign In</button>
          <button onClick={() => document.getElementById('signup-form')?.scrollIntoView({ behavior: 'smooth' })} className="px-4 py-2 bg-[#F7931E] hover:bg-[#e67e1a] text-white rounded-lg font-medium transition-all">Get Started Free</button>
        </div>
      </nav>

      {/* Hero Section */}
      <section className="max-w-6xl mx-auto px-8 py-20 text-center">
        <div className="inline-flex items-center gap-2 px-4 py-2 glass rounded-full text-sm text-[#F7931E] mb-8">
          <Zap className="w-4 h-4" />
          Save 4+ hours per week
        </div>
        <h1 className="text-5xl md:text-7xl font-bold mb-6 leading-tight">
          Save 4+ hours per week with{' '}
          <span className="gradient-text">automated invoicing</span>
          <br />and payment collection.
        </h1>
        <p className="text-xl text-slate-400 max-w-2xl mx-auto mb-10">
          Create professional invoices in 30 seconds, auto-chase late payments via personalized SMS and email sequences, and accept Stripe or PayPal payouts instantly.
        </p>
        <div className="flex justify-center gap-4">
          <button onClick={() => document.getElementById('signup-form')?.scrollIntoView({ behavior: 'smooth' })} className="px-8 py-4 bg-[#F7931E] hover:bg-[#e67e1a] text-white rounded-xl font-semibold text-lg flex items-center gap-2 transition-all">
            Get Started Free <ArrowRight className="w-5 h-5" />
          </button>
          <button className="px-8 py-4 glass hover:bg-white/5 rounded-xl font-semibold text-lg transition-all">
            See Demo
          </button>
        </div>

        {/* Hero Stats */}
        <div className="grid grid-cols-3 gap-8 mt-20 max-w-3xl mx-auto">
          <div className="text-center">
            <div className="text-3xl font-bold text-[#F7931E]">30</div>
            <div className="text-sm text-slate-400">seconds</div>
            <div className="text-xs text-slate-500">Invoice creation time</div>
          </div>
          <div className="text-center">
            <div className="text-3xl font-bold text-[#1E3A5F]">4+</div>
            <div className="text-sm text-slate-400">hours</div>
            <div className="text-xs text-slate-500">Saved per week</div>
          </div>
          <div className="text-center">
            <div className="text-3xl font-bold text-green-400">100%</div>
            <div className="text-sm text-slate-400">coverage</div>
            <div className="text-xs text-slate-500">Payment auto-chasing</div>
          </div>
        </div>
      </section>

      {/* Features Section */}
      <section className="max-w-6xl mx-auto px-8 py-20">
        <h2 className="text-3xl font-bold text-center mb-12">Everything you need to get paid faster</h2>
        <div className="grid grid-cols-1 md:grid-cols-3 gap-8">
          <div className="glass p-8 fade-in">
            <div className="w-12 h-12 bg-[#F7931E]/20 rounded-lg flex items-center justify-center mb-4">
              <Zap className="w-6 h-6 text-[#F7931E]" />
            </div>
            <h3 className="text-xl font-semibold mb-3">Automated invoicing in 30 seconds</h3>
            <p className="text-slate-400">Create professional invoices with templates and auto-fill. Send to clients instantly via email or shareable link.</p>
          </div>
          <div className="glass p-8 fade-in" style={{ animationDelay: '0.1s' }}>
            <div className="w-12 h-12 bg-[#1E3A5F]/20 rounded-lg flex items-center justify-center mb-4">
              <MessageSquare className="w-6 h-6 text-[#1E3A5F]" />
            </div>
            <h3 className="text-xl font-semibold mb-3">Auto-chase late payments</h3>
            <p className="text-slate-400">Personalized SMS and email sequences that automatically remind clients about overdue invoices. No manual follow-ups needed.</p>
          </div>
          <div className="glass p-8 fade-in" style={{ animationDelay: '0.2s' }}>
            <div className="w-12 h-12 bg-green-500/20 rounded-lg flex items-center justify-center mb-4">
              <DollarSign className="w-6 h-6 text-green-400" />
            </div>
            <h3 className="text-xl font-semibold mb-3">Accept Stripe or PayPal payouts instantly</h3>
            <p className="text-slate-400">Let clients pay with their preferred method. Get paid directly to your bank account within 2 business days.</p>
          </div>
        </div>
      </section>

      {/* Pricing Section */}
      <section className="max-w-6xl mx-auto px-8 py-20">
        <h2 className="text-3xl font-bold text-center mb-4">Simple, transparent pricing</h2>
        <p className="text-slate-400 text-center mb-12">Start free, upgrade when you need more clients</p>
        <div className="grid grid-cols-1 md:grid-cols-3 gap-8 max-w-4xl mx-auto">
          <div className="glass p-8 fade-in border border-[#F7931E]/30">
            <h3 className="text-lg font-semibold mb-2">Free</h3>
            <div className="text-3xl font-bold mb-4">$0</div>
            <p className="text-slate-400 mb-6">Perfect for getting started</p>
            <ul className="space-y-3 mb-8">
              <li className="flex items-center gap-2"><Check className="w-4 h-4 text-[#F7931E]" /> 3 clients</li>
              <li className="flex items-center gap-2"><Check className="w-4 h-4 text-[#F7931E]" /> Unlimited invoices</li>
              <li className="flex items-center gap-2"><Check className="w-4 h-4 text-[#F7931E]" /> Manual payment reminders</li>
            </ul>
            <button onClick={() => document.getElementById('signup-form')?.scrollIntoView({ behavior: 'smooth' })} className="w-full py-3 glass hover:bg-white/5 rounded-lg transition-all">Get Started Free</button>
          </div>
          <div className="glass p-8 fade-in border-2 border-[#F7931E] relative" style={{ animationDelay: '0.1s' }}>
            <div className="absolute -top-3 left-1/2 -translate-x-1/2 px-4 py-1 bg-[#F7931E] text-white text-xs font-semibold rounded-full">Most Popular</div>
            <h3 className="text-lg font-semibold mb-2">Growth</h3>
            <div className="text-3xl font-bold mb-4">$19<span className="text-lg text-slate-400">/mo</span></div>
            <p className="text-slate-400 mb-6">For growing freelancers</p>
            <ul className="space-y-3 mb-8">
              <li className="flex items-center gap-2"><Check className="w-4 h-4 text-[#F7931E]" /> Unlimited clients</li>
              <li className="flex items-center gap-2"><Check className="w-4 h-4 text-[#F7931E]" /> Auto-chase SMS & email</li>
              <li className="flex items-center gap-2"><Check className="w-4 h-4 text-[#F7931E]" /> Stripe & PayPal integration</li>
              <li className="flex items-center gap-2"><Check className="w-4 h-4 text-[#F7931E]" /> Custom invoice templates</li>
            </ul>
            <button onClick={() => document.getElementById('signup-form')?.scrollIntoView({ behavior: 'smooth' })} className="w-full py-3 bg-[#F7931E] hover:bg-[#e67e1a] text-white rounded-lg transition-all font-semibold">Start 14-Day Trial</button>
          </div>
          <div className="glass p-8 fade-in" style={{ animationDelay: '0.2s' }}>
            <h3 className="text-lg font-semibold mb-2">Teams</h3>
            <div className="text-3xl font-bold mb-4">$49<span className="text-lg text-slate-400">/mo</span></div>
            <p className="text-slate-400 mb-6">For agencies and teams</p>
            <ul className="space-y-3 mb-8">
              <li className="flex items-center gap-2"><Check className="w-4 h-4 text-[#F7931E]" /> 5 seats</li>
              <li className="flex items-center gap-2"><Check className="w-4 h-4 text-[#F7931E]" /> White-label branding</li>
              <li className="flex items-center gap-2"><Check className="w-4 h-4 text-[#F7931E]" /> Priority support</li>
              <li className="flex items-center gap-2"><Check className="w-4 h-4 text-[#F7931E]" /> Everything in Growth</li>
            </ul>
            <button onClick={() => document.getElementById('signup-form')?.scrollIntoView({ behavior: 'smooth' })} className="w-full py-3 glass hover:bg-white/5 rounded-lg transition-all">Contact Sales</button>
          </div>
        </div>
      </section>

      {/* Testimonials */}
      <section className="max-w-6xl mx-auto px-8 py-20">
        <h2 className="text-3xl font-bold text-center mb-12">Trusted by freelancers and agencies</h2>
        <div className="grid grid-cols-1 md:grid-cols-3 gap-8">
          <div className="glass p-6 fade-in">
            <div className="flex gap-1 mb-3">
              {[...Array(5)].map((_, i) => <Star key={i} className="w-4 h-4 text-[#F7931E] fill-[#F7931E]" />)}
            </div>
            <p className="text-slate-300 mb-4">"InvoiceHero saved me so much time. I used to spend hours chasing payments—now it's automatic. The 30-second invoice creation is a game changer."</p>
            <div className="flex items-center gap-3">
              <div className="w-10 h-10 bg-gradient-to-br from-[#F7931E] to-[#1E3A5F] rounded-full flex items-center justify-center text-white font-semibold">SM</div>
              <div>
                <div className="font-medium">Sarah Martinez</div>
                <div className="text-sm text-slate-400">Freelance Graphic Designer</div>
              </div>
            </div>
          </div>
          <div className="glass p-6 fade-in" style={{ animationDelay: '0.1s' }}>
            <div className="flex gap-1 mb-3">
              {[...Array(5)].map((_, i) => <Star key={i} className="w-4 h-4 text-[#F7931E] fill-[#F7931E]" />)}
            </div>
            <p className="text-slate-300 mb-4">"As a small agency owner, the Teams plan with white-label is perfect. Our clients think we built our own invoicing system!"</p>
            <div className="flex items-center gap-3">
              <div className="w-10 h-10 bg-gradient-to-br from-[#1E3A5F] to-[#F7931E] rounded-full flex items-center justify-center text-white font-semibold">KC</div>
              <div>
                <div className="font-medium">Kenji Chen</div>
                <div className="text-sm text-slate-400">Founder, StudioTen</div>
              </div>
            </div>
          </div>
          <div className="glass p-6 fade-in" style={{ animationDelay: '0.2s' }}>
            <div className="flex gap-1 mb-3">
              {[...Array(5)].map((_, i) => <Star key={i} className="w-4 h-4 text-[#F7931E] fill-[#F7931E]" />)}
            </div>
            <p className="text-slate-300 mb-4">"The SMS payment reminders have been incredible. My clients actually pay on time now. Worth every penny for the Growth plan."</p>
            <div className="flex items-center gap-3">
              <div className="w-10 h-10 bg-gradient-to-br from-green-400 to-[#1E3A5F] rounded-full flex items-center justify-center text-white font-semibold">AP</div>
              <div>
                <div className="font-medium">Amara Patel</div>
                <div className="text-sm text-slate-400">Freelance Web Developer</div>
              </div>
            </div>
          </div>
        </div>
      </section>

      {/* Signup Form */}
      <section id="signup-form" className="max-w-md mx-auto px-8 pb-20">
        <div className="glass p-8">
          <h3 className="text-xl font-semibold mb-6 text-center">Start saving 4+ hours per week</h3>
          {error && <p className="text-red-400 text-sm mb-4 text-center">{error}</p>}
          <form onSubmit={showLogin ? handleLogin : handleSignup}>
            {!showLogin && (
              <input
                value={name}
                onChange={(e) => setName(e.target.value)}
                placeholder="Your name"
                className="w-full p-3 mb-3 bg-[#0b1020] border border-[#2a3350] rounded-lg text-white placeholder-slate-500 focus:outline-none focus:border-[#F7931E]"
              />
            )}
            <input
              value={showLogin ? loginEmail : email}
              onChange={(e) => showLogin ? setLoginEmail(e.target.value) : setEmail(e.target.value)}
              placeholder="Work email"
              type="email"
              required
              className="w-full p-3 mb-3 bg-[#0b1020] border border-[#2a3350] rounded-lg text-white placeholder-slate-500 focus:outline-none focus:border-[#F7931E]"
            />
            <input
              value={showLogin ? loginPassword : password}
              onChange={(e) => showLogin ? setLoginPassword(e.target.value) : setPassword(e.target.value)}
              placeholder="Password (min 6 chars)"
              type="password"
              required
              className="w-full p-3 mb-4 bg-[#0b1020] border border-[#2a3350] rounded-lg text-white placeholder-slate-500 focus:outline-none focus:border-[#F7931E]"
            />
            <button
              type="submit"
              className="w-full py-3 bg-[#F7931E] hover:bg-[#e67e1a] text-white rounded-lg font-semibold transition-all"
            >
              {showLogin ? 'Log In' : 'Get Started Free'}
            </button>
          </form>
          <p className="text-center mt-4 text-sm text-slate-400">
            {showLogin ? "Don't have an account? " : "Already have an account? "}
            <button
              onClick={() => { setShowLogin(!showLogin); setError(''); }}
              className="text-[#F7931E] hover:underline"
            >
              {showLogin ? 'Sign up' : 'Log in'}
            </button>
          </p>
        </div>
      </section>

      {/* Footer */}
      <footer className="border-t border-white/5 py-8 text-center text-sm text-slate-500">
        &copy; 2024 InvoiceHero. All rights reserved.
      </footer>
    </div>
  );
}

function Dashboard() {
  return <div>Dashboard</div>;
}

function Invoices() {
  return <div>Invoices</div>;
}

function Clients() {
  return <div>Clients</div>;
}

function Settings() {
  return <div>Settings</div>;
}

function ProductApp({ user, onLogout }) {
  /* NC_PLACEHOLDER_DASHBOARD — replaced by the real dashboard in Phase 2 */
  return (
    <div style={{ minHeight: '100vh', background: '#0a0d18', color: '#e6eaf2', display: 'flex', flexDirection: 'column', alignItems: 'center', justifyContent: 'center', gap: 16, padding: 24, textAlign: 'center' }}>
      <h1 style={{ fontSize: 28, fontWeight: 800, margin: 0 }}>Welcome, {user?.name || user?.email || 'there'} 👋</h1>
      <p style={{ color: '#9aa6bd', maxWidth: 460, lineHeight: 1.5, margin: 0 }}>Your account is ready. Your dashboard is being set up and will appear here shortly.</p>
      <button onClick={onLogout} style={{ marginTop: 8, padding: '10px 18px', borderRadius: 10, border: '1px solid #2a3350', background: 'transparent', color: '#e6eaf2', fontWeight: 600, cursor: 'pointer' }}>Log out</button>
    </div>
  );
}

function AuthGate({ onAuth, onClose }) {
  const [mode, setMode] = useState('signup');
  const [form, setForm] = useState({ name: '', email: '', password: '' });
  const [loading, setLoading] = useState(false);
  const [error, setError] = useState('');
  const _ip = { width: '100%', padding: '11px 13px', margin: '6px 0', borderRadius: 9, border: '1px solid #2a3350', background: '#0b1020', color: '#e6eaf2', fontSize: 14, outline: 'none', boxSizing: 'border-box' };
  const submit = async (e) => {
    e.preventDefault();
    if (!form.email || !form.password) return;
    setLoading(true); setError('');
    const _b = window.__NC_BASE__ || ''; const _s = window.__COMPANY_SLUG__ || '';
    const body = JSON.stringify({ email: form.email, password: form.password, name: form.name });
    const _call = () => fetch(`${_b}/api/c/${_s}/auth/${mode}`, { method: 'POST', headers: { 'Content-Type': 'application/json' }, body });
    try {
      let res; try { res = await _call(); } catch { await new Promise(r => setTimeout(r, 2500)); res = await _call(); }
      const json = await res.json();
      if (!json.ok) { setError(json.error || 'Authentication failed — please try again'); setLoading(false); return; }
      onAuth(json);
    } catch { setError('Connection error — please try again in a moment.'); setLoading(false); }
  };
  return (
    <div onClick={onClose} style={{ position: 'fixed', inset: 0, background: 'rgba(2,6,18,.7)', backdropFilter: 'blur(4px)', display: 'flex', alignItems: 'center', justifyContent: 'center', zIndex: 1000 }}>
      <form onClick={(e) => e.stopPropagation()} onSubmit={submit} style={{ background: '#0f1424', border: '1px solid #232b45', padding: 28, borderRadius: 16, width: 360, maxWidth: '90vw', color: '#e6eaf2' }}>
        <h3 style={{ margin: '0 0 16px', fontSize: 20, fontWeight: 700 }}>{mode === 'signup' ? 'Create your account' : 'Welcome back'}</h3>
        {mode === 'signup' && <input value={form.name} onChange={(e) => setForm({ ...form, name: e.target.value })} placeholder="Your name" style={_ip} />}
        <input value={form.email} onChange={(e) => setForm({ ...form, email: e.target.value })} placeholder="Work email" type="email" required style={_ip} />
        <input value={form.password} onChange={(e) => setForm({ ...form, password: e.target.value })} placeholder="Password (min 6 chars)" type="password" required style={_ip} />
        {error && <p style={{ color: '#f87171', fontSize: 13, margin: '6px 0 0' }}>{error}</p>}
        <button type="submit" disabled={loading} style={{ width: '100%', marginTop: 10, padding: '12px', borderRadius: 9, border: 'none', background: loading ? '#4b50b8' : '#6366f1', color: '#fff', fontWeight: 700, fontSize: 15, cursor: loading ? 'default' : 'pointer' }}>
          {loading ? '…' : mode === 'signup' ? 'Get started free' : 'Log in'}
        </button>
        <p onClick={() => { setMode(mode === 'signup' ? 'login' : 'signup'); setError(''); }} style={{ marginTop: 14, fontSize: 13, color: '#9aa6bd', cursor: 'pointer', textAlign: 'center' }}>
          {mode === 'signup' ? 'Already have an account? Log in' : 'New here? Create an account'}
        </p>
      </form>
    </div>
  );
}

function App() {
  const [auth, setAuth] = useState(() => {
    try {
      if (localStorage.getItem('nc_user') && !localStorage.getItem('nc_auth')) localStorage.removeItem('nc_user');
      const a = JSON.parse(localStorage.getItem('nc_auth') || 'null');
      return (a && a.token && a.user && typeof a.user.email === 'string') ? a : null;
    } catch { return null; }
  });
  const [showAuth, setShowAuth] = useState(false);
  useEffect(() => {
    if (!auth?.token) return;
    const _b = window.__NC_BASE__ || ''; const _s = window.__COMPANY_SLUG__ || '';
    fetch(`${_b}/api/c/${_s}/auth/me`, { headers: { Authorization: `Bearer ${auth.token}` } })
      .then(r => r.json()).then(d => { if (!d.ok) { localStorage.removeItem('nc_auth'); setAuth(null); } }).catch(() => {});
  }, []);
  const onAuth = (data) => { localStorage.setItem('nc_auth', JSON.stringify(data)); setAuth(data); setShowAuth(false); };
  const onLogout = () => { localStorage.removeItem('nc_auth'); setAuth(null); };
  if (auth?.user) return <ProductApp user={auth.user} token={auth.token} onLogout={onLogout} />;
  return (
    <>
      <LandingPage onGetStarted={() => setShowAuth(true)} onSignup={() => setShowAuth(true)} onLogin={() => setShowAuth(true)} />
      {/* Fallback entry point (bottom-right so it never overlaps the nav) — guarantees a
          working login even if the landing's own buttons aren't wired to the auth modal. */}
      <button onClick={() => setShowAuth(true)} style={{ position: 'fixed', bottom: 20, right: 20, zIndex: 999, background: '#6366f1', color: '#fff', border: 'none', padding: '10px 18px', borderRadius: 999, fontWeight: 600, fontSize: 14, cursor: 'pointer', boxShadow: '0 6px 20px rgba(99,102,241,.45)' }}>Sign in</button>
      {showAuth && <AuthGate onAuth={onAuth} onClose={() => setShowAuth(false)} />}
    </>
  );
}

export default App;
