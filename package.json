import { useState, useEffect } from "react";
import { createClient } from "@supabase/supabase-js";

const SUPABASE_URL = "https://itcabbgtcbziwoorxtxh.supabase.co";
const SUPABASE_ANON_KEY = "eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJpc3MiOiJzdXBhYmFzZSIsInJlZiI6Iml0Y2FiYmd0Y2J6aXdvb3J4dHhoIiwicm9sZSI6ImFub24iLCJpYXQiOjE3NzE0MTY4OTQsImV4cCI6MjA4Njk5Mjg5NH0.D5IeVqVUgRjBDzdTAHReZd2STR0Cy4LmstXYD-0FfKE";
const supabase = createClient(SUPABASE_URL, SUPABASE_ANON_KEY);

const AGENTS = [
  {
    id: "kariyer", name: "Kariyer Koçu", emoji: "🎯",
    description: "Kariyer planı, milestone takibi, kanıt biriktirme, Copilot prompt'ları",
    color: "#c9a961", bgColor: "rgba(201,169,97,0.08)", borderColor: "rgba(201,169,97,0.25)",
    status: "active", url: "https://sekreter.vercel.app", tags: ["Kariyer", "Milestone", "Kanıt"],
  },
  {
    id: "sekreter", name: "Sekreter", emoji: "💼",
    description: "İş takvimi, Teams & email yönetimi, toplantı notları, hatırlatıcılar",
    color: "#7eb8d4", bgColor: "rgba(126,184,212,0.08)", borderColor: "rgba(126,184,212,0.25)",
    status: "coming", url: null, tags: ["İş", "Email", "Toplantı"],
  },
  {
    id: "assistant", name: "Personal Assistant", emoji: "🤖",
    description: "Kişisel randevular, sosyal ilişkiler, kişisel bildirimler & hatırlatıcılar",
    color: "#a8d4a8", bgColor: "rgba(168,212,168,0.08)", borderColor: "rgba(168,212,168,0.25)",
    status: "coming", url: null, tags: ["Kişisel", "Randevu", "Sosyal"],
  },
  {
    id: "habit", name: "Habit Tracker", emoji: "💪",
    description: "Günlük rutinler, alışkanlık zincirleri, streak takibi & ödüller",
    color: "#d4a8c9", bgColor: "rgba(212,168,201,0.08)", borderColor: "rgba(212,168,201,0.25)",
    status: "coming", url: null, tags: ["Rutin", "Alışkanlık", "Streak"],
  },
  {
    id: "diyet", name: "Diyetisyen", emoji: "🥗",
    description: "Beslenme takibi, öğün planlama, kalori & makro hedefleri",
    color: "#a8c9a8", bgColor: "rgba(168,201,168,0.08)", borderColor: "rgba(168,201,168,0.25)",
    status: "coming", url: null, tags: ["Beslenme", "Öğün", "Sağlık"],
  },
  {
    id: "psikolog", name: "Psikolog", emoji: "🧠",
    description: "Ruh hali takibi, günlük journaling, stres yönetimi & farkındalık",
    color: "#c9a8d4", bgColor: "rgba(201,168,212,0.08)", borderColor: "rgba(201,168,212,0.25)",
    status: "coming", url: null, tags: ["Mood", "Journal", "Farkındalık"],
  },
  {
    id: "cfo", name: "CFO", emoji: "💰",
    description: "Kişisel bütçe, harcama analizi, yatırım takibi, fatura & abonelik yönetimi",
    color: "#d4c97e", bgColor: "rgba(212,201,126,0.08)", borderColor: "rgba(212,201,126,0.25)",
    status: "coming", url: null, tags: ["Bütçe", "Harcama", "Yatırım"],
  },
  {
    id: "guzellik", name: "Güzellik Uzmanı", emoji: "💅",
    description: "Cilt analizi & tipi, kişisel stil oluşturma, bakım rutini, renk & ton analizi",
    color: "#d4a8b8", bgColor: "rgba(212,168,184,0.08)", borderColor: "rgba(212,168,184,0.25)",
    status: "coming", url: null, tags: ["Cilt", "Stil", "Analiz"],
  },
  {
    id: "girisim", name: "Girişim Koçu", emoji: "🚀",
    description: "Ek gelir fırsatları, freelance mentorluk, girişim fikri geliştirme & stratejisi",
    color: "#a8b8d4", bgColor: "rgba(168,184,212,0.08)", borderColor: "rgba(168,184,212,0.25)",
    status: "coming", url: null, tags: ["Girişim", "Freelance", "Gelir"],
  },
  {
    id: "housemaid", name: "Housemaid", emoji: "🏠",
    description: "Ev görevleri, alışveriş listesi, temizlik rutinleri & ev bakımı",
    color: "#d4c4a8", bgColor: "rgba(212,196,168,0.08)", borderColor: "rgba(212,196,168,0.25)",
    status: "coming", url: null, tags: ["Ev", "Alışveriş", "Temizlik"],
  },
];

function LoginScreen() {
  const [email, setEmail] = useState("");
  const [password, setPassword] = useState("");
  const [loading, setLoading] = useState(false);
  const [error, setError] = useState("");

  const handleLogin = async (e) => {
    e.preventDefault();
    setLoading(true);
    setError("");
    const { error } = await supabase.auth.signInWithPassword({ email, password });
    if (error) setError("Email veya şifre hatalı.");
    setLoading(false);
  };

  return (
    <div style={{
      minHeight: "100vh",
      background: "linear-gradient(160deg, #080d12 0%, #0f1a24 40%, #08121a 100%)",
      fontFamily: "'Cormorant Garamond', Georgia, serif",
      display: "flex", alignItems: "center", justifyContent: "center",
      position: "relative", overflow: "hidden",
    }}>
      <div style={{
        position: "fixed", inset: 0, pointerEvents: "none",
        backgroundImage: `linear-gradient(rgba(201,169,97,0.03) 1px, transparent 1px), linear-gradient(90deg, rgba(201,169,97,0.03) 1px, transparent 1px)`,
        backgroundSize: "60px 60px",
      }} />
      <div style={{
        position: "fixed", top: "-10%", left: "50%", transform: "translateX(-50%)",
        width: 600, height: 300,
        background: "radial-gradient(ellipse, rgba(201,169,97,0.08) 0%, transparent 70%)",
        pointerEvents: "none",
      }} />

      <div style={{ position: "relative", zIndex: 1, width: "100%", maxWidth: 400, padding: "0 24px" }}>
        <div style={{ textAlign: "center", marginBottom: 40 }}>
          <div style={{ fontSize: 11, letterSpacing: 4, color: "#c9a961", textTransform: "uppercase", marginBottom: 16 }}>
            ◆ AI Agent Ekosistemi
          </div>
          <div style={{ fontSize: 36, fontWeight: 700, color: "#fff", marginBottom: 8 }}>Hoş geldin</div>
          <div style={{ fontSize: 14, color: "#6a5a40", fontStyle: "italic" }}>
            Kişisel asistan sistemine giriş yap
          </div>
        </div>

        <form onSubmit={handleLogin} style={{ display: "flex", flexDirection: "column", gap: 14 }}>
          <input
            type="email" value={email} onChange={e => setEmail(e.target.value)}
            placeholder="Email" required
            style={{
              background: "rgba(245,235,215,0.04)", border: "1px solid rgba(245,235,215,0.1)",
              borderRadius: 12, padding: "14px 18px", color: "#f5f1e8", fontSize: 15,
              outline: "none", fontFamily: "inherit",
            }}
          />
          <input
            type="password" value={password} onChange={e => setPassword(e.target.value)}
            placeholder="Şifre" required
            style={{
              background: "rgba(245,235,215,0.04)", border: "1px solid rgba(245,235,215,0.1)",
              borderRadius: 12, padding: "14px 18px", color: "#f5f1e8", fontSize: 15,
              outline: "none", fontFamily: "inherit",
            }}
          />
          {error && <div style={{ fontSize: 13, color: "#e74c3c", textAlign: "center" }}>{error}</div>}
          <button type="submit" disabled={loading} style={{
            background: loading ? "rgba(201,169,97,0.3)" : "linear-gradient(135deg, #c9a961, #b89850)",
            border: "none", borderRadius: 12, padding: "14px",
            color: "#fff", fontSize: 15, fontWeight: 700,
            cursor: loading ? "not-allowed" : "pointer",
            marginTop: 8, fontFamily: "inherit", transition: "all 0.2s",
          }}>
            {loading ? "Giriş yapılıyor..." : "Giriş Yap →"}
          </button>
        </form>
      </div>
    </div>
  );
}

export default function Dashboard() {
  const [session, setSession] = useState(null);
  const [authLoading, setAuthLoading] = useState(true);
  const [hoveredId, setHoveredId] = useState(null);
  const [time, setTime] = useState(new Date());

  useEffect(() => {
    supabase.auth.getSession().then(({ data: { session } }) => {
      setSession(session);
      setAuthLoading(false);
    });
    const { data: { subscription } } = supabase.auth.onAuthStateChange((_event, session) => {
      setSession(session);
    });
    return () => subscription.unsubscribe();
  }, []);

  useEffect(() => {
    const timer = setInterval(() => setTime(new Date()), 1000);
    return () => clearInterval(timer);
  }, []);

  if (authLoading) return (
    <div style={{
      minHeight: "100vh", background: "#080d12",
      display: "flex", alignItems: "center", justifyContent: "center",
      color: "#c9a961", fontFamily: "Georgia, serif", fontSize: 14,
    }}>⏳ Yükleniyor...</div>
  );

  if (!session) return <LoginScreen />;

  const activeAgents = AGENTS.filter(a => a.status === "active");
  const comingAgents = AGENTS.filter(a => a.status === "coming");

  const greeting = () => {
    const h = time.getHours();
    if (h < 12) return "Günaydın";
    if (h < 18) return "İyi günler";
    return "İyi akşamlar";
  };

  return (
    <div style={{
      minHeight: "100vh",
      background: "linear-gradient(160deg, #080d12 0%, #0f1a24 40%, #08121a 100%)",
      fontFamily: "'Cormorant Garamond', 'Playfair Display', Georgia, serif",
      color: "#f5f1e8", position: "relative", overflow: "hidden",
    }}>
      <div style={{
        position: "fixed", inset: 0, pointerEvents: "none", zIndex: 0,
        backgroundImage: `linear-gradient(rgba(201,169,97,0.03) 1px, transparent 1px), linear-gradient(90deg, rgba(201,169,97,0.03) 1px, transparent 1px)`,
        backgroundSize: "60px 60px",
      }} />
      <div style={{
        position: "fixed", top: "-20%", left: "50%", transform: "translateX(-50%)",
        width: 800, height: 400,
        background: "radial-gradient(ellipse, rgba(201,169,97,0.06) 0%, transparent 70%)",
        pointerEvents: "none", zIndex: 0,
      }} />

      <div style={{ position: "relative", zIndex: 1, maxWidth: 1100, margin: "0 auto", padding: "48px 24px" }}>

        {/* Header */}
        <div style={{ marginBottom: 56 }}>
          <div style={{ display: "flex", justifyContent: "space-between", alignItems: "flex-start", flexWrap: "wrap", gap: 20 }}>
            <div>
              <div style={{ fontSize: 11, letterSpacing: 4, color: "#c9a961", textTransform: "uppercase", marginBottom: 12 }}>
                ◆ Burcu Gürel · AI Agent Ekosistemi
              </div>
              <h1 style={{ fontSize: 42, fontWeight: 700, color: "#fff", margin: 0, lineHeight: 1.1 }}>
                {greeting()}, Burcu
              </h1>
              <p style={{ fontSize: 16, color: "#8a7860", marginTop: 10, fontStyle: "italic" }}>
                Kişisel AI agent'larına buradan ulaş
              </p>
            </div>

            <div style={{ display: "flex", flexDirection: "column", alignItems: "flex-end", gap: 12 }}>
              <div style={{
                background: "rgba(201,169,97,0.06)", border: "1px solid rgba(201,169,97,0.15)",
                borderRadius: 16, padding: "16px 24px", textAlign: "center", minWidth: 140,
              }}>
                <div style={{ fontSize: 28, fontWeight: 700, color: "#c9a961", letterSpacing: 2, fontFamily: "monospace" }}>
                  {time.toLocaleTimeString("tr-TR", { hour: "2-digit", minute: "2-digit" })}
                </div>
                <div style={{ fontSize: 11, color: "#8a7860", marginTop: 4 }}>
                  {time.toLocaleDateString("tr-TR", { weekday: "long", day: "numeric", month: "long" })}
                </div>
              </div>
              <button onClick={() => supabase.auth.signOut()} style={{
                background: "transparent", border: "1px solid rgba(245,235,215,0.08)",
                borderRadius: 8, padding: "6px 14px", color: "#6a5a40",
                fontSize: 12, cursor: "pointer", fontFamily: "inherit",
              }}>
                Çıkış Yap
              </button>
            </div>
          </div>

          <div style={{
            display: "flex", gap: 24, marginTop: 32, padding: "16px 24px",
            background: "rgba(245,235,215,0.03)", border: "1px solid rgba(245,235,215,0.06)",
            borderRadius: 12, flexWrap: "wrap",
          }}>
            <div style={{ display: "flex", alignItems: "center", gap: 10 }}>
              <div style={{ width: 8, height: 8, borderRadius: "50%", background: "#3d9970" }} />
              <span style={{ fontSize: 13, color: "#b8a890" }}>
                <strong style={{ color: "#f5f1e8" }}>{activeAgents.length}</strong> aktif agent
              </span>
            </div>
            <div style={{ width: 1, background: "rgba(245,235,215,0.08)" }} />
            <div style={{ display: "flex", alignItems: "center", gap: 10 }}>
              <div style={{ width: 8, height: 8, borderRadius: "50%", background: "#c9a961", opacity: 0.5 }} />
              <span style={{ fontSize: 13, color: "#b8a890" }}>
                <strong style={{ color: "#f5f1e8" }}>{comingAgents.length}</strong> yapım aşamasında
              </span>
            </div>
            <div style={{ width: 1, background: "rgba(245,235,215,0.08)" }} />
            <span style={{ fontSize: 13, color: "#b8a890" }}>
              <strong style={{ color: "#f5f1e8" }}>{AGENTS.length}</strong> toplam agent
            </span>
          </div>
        </div>

        {/* Active */}
        <div style={{ marginBottom: 48 }}>
          <div style={{
            fontSize: 11, letterSpacing: 3, color: "#3d9970", textTransform: "uppercase",
            marginBottom: 20, display: "flex", alignItems: "center", gap: 8,
          }}>
            <div style={{ width: 6, height: 6, borderRadius: "50%", background: "#3d9970" }} />
            Aktif
          </div>
          <div style={{ display: "grid", gridTemplateColumns: "repeat(auto-fill, minmax(300px, 1fr))", gap: 20 }}>
            {activeAgents.map(agent => (
              <AgentCard key={agent.id} agent={agent} hovered={hoveredId === agent.id} onHover={setHoveredId} />
            ))}
          </div>
        </div>

        {/* Coming Soon */}
        <div>
          <div style={{
            fontSize: 11, letterSpacing: 3, color: "#c9a961", textTransform: "uppercase",
            marginBottom: 20, display: "flex", alignItems: "center", gap: 8,
          }}>
            <div style={{ width: 6, height: 6, borderRadius: "50%", background: "#c9a961", opacity: 0.5 }} />
            Yapım Aşamasında
          </div>
          <div style={{ display: "grid", gridTemplateColumns: "repeat(auto-fill, minmax(260px, 1fr))", gap: 16 }}>
            {comingAgents.map(agent => (
              <AgentCard key={agent.id} agent={agent} hovered={hoveredId === agent.id} onHover={setHoveredId} />
            ))}
          </div>
        </div>

        <div style={{ marginTop: 64, paddingTop: 24, borderTop: "1px solid rgba(245,235,215,0.06)", textAlign: "center" }}>
          <div style={{ fontSize: 12, color: "#4a3f30", letterSpacing: 2 }}>
            BURCU GÜREL · KİŞİSEL AI EKOSİSTEMİ · {new Date().getFullYear()}
          </div>
        </div>
      </div>
    </div>
  );
}

function AgentCard({ agent, hovered, onHover }) {
  const isActive = agent.status === "active";
  return (
    <div
      onMouseEnter={() => onHover(agent.id)}
      onMouseLeave={() => onHover(null)}
      onClick={() => isActive && agent.url && window.open(agent.url, "_blank")}
      style={{
        background: hovered && isActive ? agent.bgColor : "rgba(245,235,215,0.02)",
        border: `1px solid ${hovered && isActive ? agent.borderColor : "rgba(245,235,215,0.07)"}`,
        borderRadius: 16, padding: "24px",
        cursor: isActive ? "pointer" : "default",
        transition: "all 0.3s ease",
        opacity: isActive ? 1 : 0.45,
        transform: hovered && isActive ? "translateY(-2px)" : "none",
        boxShadow: hovered && isActive ? `0 8px 32px ${agent.bgColor}` : "none",
        position: "relative", overflow: "hidden",
      }}
    >
      {isActive && (
        <div style={{
          position: "absolute", top: 16, right: 16,
          width: 8, height: 8, borderRadius: "50%", background: "#3d9970",
          boxShadow: "0 0 8px rgba(61,153,112,0.6)",
        }} />
      )}
      {!isActive && (
        <div style={{
          position: "absolute", top: 14, right: 14, fontSize: 9, letterSpacing: 1.5,
          color: "#6a5a40", textTransform: "uppercase",
          background: "rgba(245,235,215,0.04)", border: "1px solid rgba(245,235,215,0.08)",
          borderRadius: 6, padding: "3px 8px",
        }}>Yakında</div>
      )}
      <div style={{ fontSize: 32, marginBottom: 14 }}>{agent.emoji}</div>
      <div style={{ fontSize: 18, fontWeight: 700, color: isActive ? "#f5f1e8" : "#6a5a40", marginBottom: 8 }}>
        {agent.name}
      </div>
      <div style={{ fontSize: 13, color: isActive ? "#b8a890" : "#4a3f30", lineHeight: 1.6, marginBottom: 16 }}>
        {agent.description}
      </div>
      <div style={{ display: "flex", gap: 6, flexWrap: "wrap" }}>
        {agent.tags.map(tag => (
          <span key={tag} style={{
            fontSize: 10, letterSpacing: 1,
            color: isActive ? agent.color : "#4a3f30",
            background: isActive ? agent.bgColor : "transparent",
            border: `1px solid ${isActive ? agent.borderColor : "rgba(245,235,215,0.05)"}`,
            borderRadius: 20, padding: "3px 10px", textTransform: "uppercase",
          }}>{tag}</span>
        ))}
      </div>
      {isActive && hovered && (
        <div style={{ position: "absolute", bottom: 20, right: 20, fontSize: 16, color: agent.color }}>→</div>
      )}
    </div>
  );
}
