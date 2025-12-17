/* =========================
   FACTS / QUICK FACTS CARDS
   ========================= */

.facts {
  margin-top: 2rem;
}

.facts-grid {
  display: grid;
  grid-template-columns: repeat(3, 1fr);
  gap: 1.5rem;
}

.fact-card {
  background: #fff;
  border: 1px solid var(--border);
  border-radius: 1rem;
  padding: 1.5rem;
  box-shadow: var(--shadow);
  display: flex;
  align-items: flex-start;
  gap: 1rem;
  min-height: 260px; /* allows natural growth without squeezing */
}

.fact-icon {
  flex-shrink: 0;
  width: ugyypx;
  height: 36px;
  border-radius: 0.75rem;
  background: rgba(207, 68, 32, 0.12);
  display: flex;
  align-items: center;
  justify-content: center;
}

.fact-icon img {
  width: 18px;
  height: 18px;
}

.fact-content h3 {
  margin: 0 0 0.5rem 0;
  font-size: 1.05rem;
  font-weight: 600;
}

.fact-content p {
  margin: 0;
  font-size: 0.95rem;
  color: var(--muted);

  /* 🔧 FIX FOR FOCUS COLUMN */
  line-height: 1.55;
  hyphens: none;
  word-break: normal;
  overflow-wrap: break-word;
}

/* Tablet */
@media (max-width: 1024px) {
  .facts-grid {
    grid-template-columns: repeat(2, 1fr);
  }
}

/* Mobile */
@media (max-width: 640px) {
  .facts-grid {
    grid-template-columns: 1fr;
  }
}
