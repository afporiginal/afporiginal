import { useState } from 'react';
import readmeRaw from '../README.md?raw';
import marinAvatarImg from '/images/marin-avatar.png';
import marinRenderImg from '/images/marin-render.png';
import marinCosplay1Img from '/images/marin-cosplay1.png';
import marinCosplay2Img from '/images/marin-cosplay2.png';
import marinCosplay3Img from '/images/marin-cosplay3.png';
import marinCosplay4Img from '/images/marin-cosplay4.png';

function App() {
  const [copied, setCopied] = useState(false);
  const [tab, setTab] = useState<'preview' | 'code'>('preview');

  const handleCopy = () => {
    navigator.clipboard.writeText(readmeRaw);
    setCopied(true);
    setTimeout(() => setCopied(false), 2500);
  };

  const marinAvatar = marinAvatarImg;
  const marinRender = marinRenderImg;
  const marinCosplays = [
    marinCosplay1Img,
    marinCosplay2Img,
    marinCosplay3Img,
    marinCosplay4Img,
  ];

  return (
    <div className="min-h-screen bg-[#0d1117] text-[#c9d1d9] font-sans">
      {/* Header */}
      <div className="sticky top-0 z-50 border-b border-[#30363d] bg-[#161b22]/95 backdrop-blur-md">
        <div className="max-w-5xl mx-auto px-4 py-3 flex items-center justify-between flex-wrap gap-3">
          <div className="flex items-center gap-3">
            <div className="w-8 h-8 rounded-full bg-gradient-to-br from-pink-400 to-rose-500 flex items-center justify-center text-white font-bold text-xs">MK</div>
            <div>
              <h1 className="text-sm font-semibold text-white">afporiginal / README.md</h1>
              <p className="text-xs text-[#8b949e]">Exemplo com Marin Kitagawa — veja como fica com imagens!</p>
            </div>
          </div>
          <div className="flex items-center gap-2">
            <div className="flex rounded-lg overflow-hidden border border-[#30363d]">
              <button onClick={() => setTab('preview')} className={`px-4 py-1.5 text-xs font-medium transition-colors ${tab === 'preview' ? 'bg-[#30363d] text-white' : 'text-[#8b949e] hover:text-white'}`}>👁 Preview</button>
              <button onClick={() => setTab('code')} className={`px-4 py-1.5 text-xs font-medium transition-colors ${tab === 'code' ? 'bg-[#30363d] text-white' : 'text-[#8b949e] hover:text-white'}`}>{'<>'} Code</button>
            </div>
            <button onClick={handleCopy} className="px-4 py-1.5 rounded-lg bg-[#238636] hover:bg-[#2ea043] text-white text-xs font-semibold transition-colors">
              {copied ? '✓ Copiado!' : '📋 Copiar README'}
            </button>
          </div>
        </div>
      </div>

      {/* Example banner */}
      <div className="bg-gradient-to-r from-pink-500/10 via-rose-500/10 to-purple-500/10 border-b border-pink-500/20">
        <div className="max-w-5xl mx-auto px-4 py-3 flex items-center gap-3">
          <span className="text-lg">🎀</span>
          <div>
            <p className="text-sm text-pink-300 font-medium">Isso é um <strong>exemplo</strong> — com a Marin Kitagawa como modelo!</p>
            <p className="text-xs text-[#8b949e]">Mostra como o README fica quando você substitui os <code className="text-yellow-400 bg-yellow-400/10 px-1 rounded">COLE_O_LINK_...</code> por URLs reais de imagens.</p>
          </div>
        </div>
      </div>

      {tab === 'preview' ? (
        <div className="max-w-5xl mx-auto px-4 py-8">
          <div className="border border-[#30363d] rounded-lg bg-[#0d1117] overflow-hidden">
            <div className="px-4 py-3 border-b border-[#30363d] bg-[#161b22] flex items-center gap-2">
              <svg width="16" height="16" viewBox="0 0 16 16" fill="#8b949e"><path d="M2 1.75C2 .784 2.784 0 3.75 0h6.586c.464 0 .909.184 1.237.513l2.914 2.914c.329.328.513.773.513 1.237v9.586A1.75 1.75 0 0 1 13.25 16h-9.5A1.75 1.75 0 0 1 2 14.25Zm1.75-.25a.25.25 0 0 0-.25.25v12.5c0 .138.112.25.25.25h9.5a.25.25 0 0 0 .25-.25V6h-2.75A1.75 1.75 0 0 1 9 4.25V1.5Zm6.75.062V4.25c0 .138.112.25.25.25h2.688l-.011-.013-2.914-2.914-.013-.011Z"></path></svg>
              <span className="text-sm text-[#c9d1d9] font-semibold">README.md</span>
              <span className="text-xs bg-pink-500/20 text-pink-400 px-2 py-0.5 rounded-full ml-2">Exemplo Marin</span>
            </div>

            <div className="p-6 space-y-4">
              {/* Header wave */}
              <img src="https://capsule-render.vercel.app/api?type=waving&color=0:0d1117,25:1a0533,50:a855f7,75:00d4ff,100:0d1117&height=220&section=header&text=&fontSize=0" className="w-full" alt="Header" />

              {/* ✅ AVATAR COM IMAGEM REAL */}
              <div className="text-center">
                <img src={marinAvatar} width="280" className="rounded-2xl shadow-lg shadow-purple-500/20 mx-auto" alt="Marin Kitagawa Avatar"/>
              </div>

              {/* Typing SVGs */}
              <div className="text-center space-y-1">
                <img src="https://readme-typing-svg.demolab.com?font=JetBrains+Mono&weight=700&size=28&duration=3000&pause=1000&color=A855F7&center=true&vCenter=true&repeat=true&random=false&width=700&height=45&lines=👋+Fala!+Eu+sou+o+AFPL" alt="Typing" />
                <br/>
                <img src="https://readme-typing-svg.demolab.com?font=JetBrains+Mono&weight=400&size=16&duration=2500&pause=800&color=8b949e&center=true&vCenter=true&repeat=true&random=false&width=700&height=30&lines=Python+Developer+🐍+%7C+Lua+Scripter+🌙+%7C+3D+Artist+🎨;Bot+Architect+🤖+%7C+Gaming+Visionary+🎮+%7C+Blender+Enthusiast+🧊;Full-Stack+Innovator+💡+%7C+Automating+the+Ordinary+⚡" alt="Typing2" />
              </div>

              {/* Dynamic badges */}
              <div className="text-center flex flex-wrap justify-center gap-2">
                <img src="https://img.shields.io/badge/dynamic/json?logo=github&label=Repos&style=for-the-badge&color=0d1117&labelColor=1a1b27&query=%24.public_repos&url=https%3A%2F%2Fapi.github.com%2Fusers%2Fafporiginal" alt="Repos"/>
                <img src="https://img.shields.io/badge/dynamic/json?logo=github&label=Followers&style=for-the-badge&color=0d1117&labelColor=1a1b27&query=%24.followers&url=https%3A%2F%2Fapi.github.com%2Fusers%2Fafporiginal" alt="Followers"/>
                <img src="https://komarev.com/ghpvc/?username=afporiginal&style=for-the-badge&color=a855f7&labelColor=1a1b27&label=VIEWS" alt="Views"/>
              </div>

              <img src="https://user-images.githubusercontent.com/73097560/115834477-dbab4500-a447-11eb-908a-139a6edaec5c.gif" className="w-full" alt="divider"/>

              {/* About + ✅ RENDER LATERAL COM IMAGEM REAL */}
              <div className="grid md:grid-cols-2 gap-6">
                <div>
                  <h2 className="text-xl font-semibold text-white border-b border-[#30363d] pb-2 mb-4 flex items-center gap-2">
                    <img src="https://media.giphy.com/media/WUlplcMpOCEmTGBtBW/giphy.gif" width="28" alt="" /> Sobre Mim
                  </h2>
                  <div className="bg-[#161b22] border border-[#30363d] rounded-lg p-4 overflow-x-auto">
                    <pre className="text-[11px] font-mono text-[#c9d1d9] whitespace-pre leading-relaxed"><code><span className="text-[#ff7b72]">class</span> <span className="text-[#d2a8ff]">AFPL</span> {'{\n'}    <span className="text-[#d2a8ff]">constructor</span>() {'{\n'}        <span className="text-[#ff7b72]">this</span>.<span className="text-[#79c0ff]">name</span>     = <span className="text-[#a5d6ff]">"AFPL"</span>;{'\n'}        <span className="text-[#ff7b72]">this</span>.<span className="text-[#79c0ff]">aka</span>      = <span className="text-[#a5d6ff]">"afporiginal"</span>;{'\n'}        <span className="text-[#ff7b72]">this</span>.<span className="text-[#79c0ff]">location</span> = <span className="text-[#a5d6ff]">"Brazil 🇧🇷"</span>;{'\n'}    {'}\n\n'}    <span className="text-[#ff7b72]">get</span> <span className="text-[#d2a8ff]">skills</span>() {'{\n'}        <span className="text-[#ff7b72]">return</span> {'{\n'}            <span className="text-[#79c0ff]">code</span>:    [<span className="text-[#a5d6ff]">"Python"</span>, <span className="text-[#a5d6ff]">"Lua"</span>, <span className="text-[#a5d6ff]">"JS"</span>, <span className="text-[#a5d6ff]">"TS"</span>],{'\n'}            <span className="text-[#79c0ff]">create</span>:  [<span className="text-[#a5d6ff]">"Blender 3D"</span>, <span className="text-[#a5d6ff]">"Roblox"</span>],{'\n'}            <span className="text-[#79c0ff]">automate</span>:[<span className="text-[#a5d6ff]">"Discord Bots"</span>, <span className="text-[#a5d6ff]">"APIs"</span>],{'\n'}        {'};'}{'\n'}    {'}\n}'}</code></pre>
                  </div>
                </div>
                <div className="flex items-center justify-center">
                  <img src={marinRender} width="380" className="rounded-2xl shadow-lg shadow-cyan-500/20" alt="3D Render"/>
                </div>
              </div>

              <img src="https://user-images.githubusercontent.com/73097560/115834477-dbab4500-a447-11eb-908a-139a6edaec5c.gif" className="w-full" alt="divider"/>

              {/* Tech Stack */}
              <h2 className="text-xl font-semibold text-white border-b border-[#30363d] pb-2 mb-4 flex items-center gap-2">
                <img src="https://media2.giphy.com/media/QssGEmpkyEOhBCb7e1/giphy.gif?cid=ecf05e47a0n3gi1bfqntqmob8g9aid1oyj2wr3ds3mg700bl&rid=giphy.gif" width="25" alt="" /> Tech Stack
              </h2>
              <div className="grid grid-cols-2 md:grid-cols-4 gap-3 mb-2">
                {[
                  { title: '🔥 Languages', icons: 'python,lua,js,ts,html,css' },
                  { title: '🛠️ Tools', icons: 'nodejs,git,vscode,docker,linux,bash' },
                  { title: '🎯 Platforms', icons: 'discord,github,robloxstudio,vercel,cloudflare,heroku' },
                  { title: '🎨 Creative', icons: 'blender,figma,ps,ae,unity,godot' },
                ].map((cat) => (
                  <div key={cat.title} className="bg-[#161b22] border border-[#30363d] rounded-lg p-4 text-center">
                    <p className="text-xs font-semibold text-white mb-3">{cat.title}</p>
                    <img src={`https://skillicons.dev/icons?i=${cat.icons}&perline=3`} alt={cat.title} className="mx-auto"/>
                  </div>
                ))}
              </div>

              <img src="https://user-images.githubusercontent.com/73097560/115834477-dbab4500-a447-11eb-908a-139a6edaec5c.gif" className="w-full" alt="divider"/>

              {/* ✅ GALERIA DE RENDERS COM IMAGENS REAIS */}
              <h2 className="text-xl font-semibold text-white border-b border-[#30363d] pb-2 mb-2">🧊 Blender & 3D Art</h2>
              <p className="text-sm text-[#8b949e] text-center italic mb-4">Ultimamente tenho mergulhado no mundo da modelagem 3D — criando personagens, cenários e assets.</p>
              <div className="grid grid-cols-2 gap-3">
                {[
                  { img: marinCosplays[0], label: '🎨 Magical Girl — Cosplay render' },
                  { img: marinCosplays[1], label: '🖤 Gothic Lolita — Dark aesthetic' },
                  { img: marinCosplays[2], label: '🌸 School Uniform — Casual vibes' },
                  { img: marinCosplays[3], label: '⚔️ Fantasy Warrior — Epic render' },
                ].map((r, i) => (
                  <div key={i} className="text-center">
                    <img src={r.img} className="w-full rounded-xl shadow-lg" alt={`Render ${i+1}`}/>
                    <p className="text-xs text-[#8b949e] mt-2">{r.label}</p>
                  </div>
                ))}
              </div>

              <img src="https://user-images.githubusercontent.com/73097560/115834477-dbab4500-a447-11eb-908a-139a6edaec5c.gif" className="w-full" alt="divider"/>

              {/* What defines me */}
              <h2 className="text-xl font-semibold text-white border-b border-[#30363d] pb-2 mb-4">⚡ O que me define</h2>
              <div className="grid grid-cols-2 md:grid-cols-3 gap-3">
                {[
                  { icon: '💻', title: 'Developer', text: 'Python, Lua e JS para apps escaláveis' },
                  { icon: '🧊', title: '3D Artist', text: 'Modelos e cenários no Blender' },
                  { icon: '🤖', title: 'Bot Architect', text: 'Bots avançados no Discord' },
                  { icon: '🎮', title: 'Game Dev', text: 'Experiências imersivas no Roblox' },
                  { icon: '💡', title: 'Innovator', text: 'Soluções criativas' },
                  { icon: '📈', title: 'Learner', text: 'Sempre evoluindo' },
                ].map((item, i) => (
                  <div key={i} className="bg-[#161b22] border border-[#30363d] rounded-lg p-4 text-center">
                    <span className="text-2xl">{item.icon}</span>
                    <h3 className="text-sm font-semibold text-white mt-1">{item.title}</h3>
                    <p className="text-xs text-[#8b949e] mt-1">{item.text}</p>
                  </div>
                ))}
              </div>

              <img src="https://user-images.githubusercontent.com/73097560/115834477-dbab4500-a447-11eb-908a-139a6edaec5c.gif" className="w-full" alt="divider"/>

              {/* GitHub Analytics */}
              <h2 className="text-xl font-semibold text-white border-b border-[#30363d] pb-2 mb-4">📊 GitHub Analytics</h2>
              <div className="text-center space-y-3">
                <div className="flex flex-wrap justify-center gap-4">
                  <img src="https://github-readme-stats.vercel.app/api?username=afporiginal&show_icons=true&theme=radical&hide_border=true&bg_color=0D1117&title_color=A855F7&icon_color=00D4FF&text_color=C9D1D9&ring_color=A855F7&count_private=true&include_all_commits=true" height="165" alt="Stats" />
                  <img src="https://github-readme-stats.vercel.app/api/top-langs/?username=afporiginal&layout=compact&theme=radical&hide_border=true&bg_color=0D1117&title_color=A855F7&text_color=C9D1D9&langs_count=10" height="165" alt="Top Langs" />
                </div>
                <img src="https://github-readme-streak-stats.herokuapp.com/?user=afporiginal&theme=radical&hide_border=true&background=0D1117&stroke=A855F7&ring=A855F7&fire=00D4FF&currStreakLabel=A855F7&sideLabels=A855F7&currStreakNum=C9D1D9&sideNums=C9D1D9&dates=555555" alt="Streak" />
                <img src="https://github-readme-activity-graph.vercel.app/graph?username=afporiginal&bg_color=0D1117&color=A855F7&line=00D4FF&point=A855F7&area=true&area_color=A855F7&hide_border=true&custom_title=📈%20Contribution%20Graph" className="w-full" alt="Graph" />
                <img src="https://github-profile-trophy.vercel.app/?username=afporiginal&theme=radical&no-frame=true&no-bg=true&column=7&margin-w=10" alt="Trophies" />
              </div>

              <img src="https://user-images.githubusercontent.com/73097560/115834477-dbab4500-a447-11eb-908a-139a6edaec5c.gif" className="w-full" alt="divider"/>

              {/* Projects */}
              <h2 className="text-xl font-semibold text-white border-b border-[#30363d] pb-2 mb-4">🚀 Projetos em Destaque</h2>
              <div className="overflow-x-auto">
                <table className="w-full text-sm">
                  <thead>
                    <tr className="border-b border-[#30363d]">
                      <th className="py-2 px-2 w-8"></th>
                      <th className="text-left py-2 px-2 text-[#8b949e] font-medium">Projeto</th>
                      <th className="text-left py-2 px-2 text-[#8b949e] font-medium">Descrição</th>
                      <th className="text-left py-2 px-2 text-[#8b949e] font-medium">Tech</th>
                      <th className="text-center py-2 px-2 text-[#8b949e] font-medium">Status</th>
                    </tr>
                  </thead>
                  <tbody>
                    {[
                      { icon: '⚔️', name: 'Roblox RPG Engine', desc: 'Engine completa de RPG', tech: 'Lua · Roblox', status: 'Ativo', c: '#22c55e' },
                      { icon: '🤖', name: 'Discord Bot Framework', desc: 'Bot modular com AI', tech: 'Python · Discord.py', status: 'Ativo', c: '#22c55e' },
                      { icon: '🧊', name: 'Blender Assets Pack', desc: 'Modelos 3D para games', tech: 'Blender · FBX', status: 'Em Progresso', c: '#eab308' },
                      { icon: '⚡', name: 'Automation Suite', desc: 'Scripts de scraping', tech: 'Python · Selenium', status: 'Concluído', c: '#3b82f6' },
                      { icon: '🎵', name: 'Music Bot Plus', desc: 'Bot de música completo', tech: 'Python · FFmpeg', status: 'Ativo', c: '#22c55e' },
                    ].map((p, i) => (
                      <tr key={i} className="border-b border-[#21262d] hover:bg-[#161b22]">
                        <td className="py-2 px-2 text-center">{p.icon}</td>
                        <td className="py-2 px-2 font-semibold text-white whitespace-nowrap">{p.name}</td>
                        <td className="py-2 px-2 text-[#8b949e]">{p.desc}</td>
                        <td className="py-2 px-2"><code className="text-xs bg-[#21262d] px-1.5 py-0.5 rounded">{p.tech}</code></td>
                        <td className="py-2 px-2 text-center"><span className="text-xs font-medium px-2 py-0.5 rounded-full" style={{ backgroundColor: p.c + '20', color: p.c }}>{p.status}</span></td>
                      </tr>
                    ))}
                  </tbody>
                </table>
              </div>

              <img src="https://user-images.githubusercontent.com/73097560/115834477-dbab4500-a447-11eb-908a-139a6edaec5c.gif" className="w-full" alt="divider"/>

              {/* Quote */}
              <div className="text-center mb-2">
                <img src="https://quotes-github-readme.vercel.app/api?type=horizontal&theme=radical" alt="Quote" />
              </div>

              <img src="https://user-images.githubusercontent.com/73097560/115834477-dbab4500-a447-11eb-908a-139a6edaec5c.gif" className="w-full" alt="divider"/>

              {/* Connect */}
              <h2 className="text-xl font-semibold text-white border-b border-[#30363d] pb-2 mb-4">📬 Vamos Conectar</h2>
              <div className="text-center space-y-3">
                <div className="flex flex-wrap justify-center gap-2">
                  <img src="https://img.shields.io/badge/Email-afploriginal.luz07-EA4335?style=for-the-badge&logo=gmail&logoColor=white" alt="Email" />
                  <img src="https://img.shields.io/badge/Discord-afploriginal-5865F2?style=for-the-badge&logo=discord&logoColor=white" alt="Discord" />
                  <img src="https://img.shields.io/badge/GitHub-afporiginal-181717?style=for-the-badge&logo=github&logoColor=white" alt="GitHub" />
                </div>
                <p className="text-base font-medium italic text-white">💡 "The future belongs to those who believe in the beauty of their dreams."</p>
                <blockquote className="border-l-4 border-purple-500 pl-4 text-[#8b949e] font-medium inline-block text-left">🌌 Criatividade não tem limites — vamos construir algo extraordinário!</blockquote>
              </div>

              <img src="https://capsule-render.vercel.app/api?type=waving&color=0:0d1117,25:1a0533,50:a855f7,75:00d4ff,100:0d1117&height=120&section=footer" className="w-full mt-6" alt="Footer" />
            </div>
          </div>

          {/* How to use card */}
          <div className="mt-8 border border-pink-500/30 rounded-lg bg-pink-500/5 p-6">
            <h3 className="text-lg font-semibold text-pink-400 mb-3">🎀 Como fazer igual com as SUAS imagens</h3>
            <div className="space-y-4 text-sm text-[#8b949e]">
              <p>Esse exemplo usa a Marin Kitagawa. No seu caso, é só trocar pelas <strong className="text-white">suas</strong> imagens (anime que você criou, renders do Blender, etc).</p>
              
              <div className="bg-[#161b22] border border-[#30363d] rounded-lg p-4">
                <p className="font-semibold text-white mb-2">Passo a passo:</p>
                <ol className="space-y-2 list-decimal list-inside text-[#8b949e]">
                  <li>Envie sua imagem no <strong className="text-white">Discord</strong> (qualquer canal)</li>
                  <li>Clique com <strong className="text-white">botão direito</strong> na imagem → <strong className="text-white">"Copiar link"</strong></li>
                  <li>No README, troque <code className="text-yellow-400 bg-yellow-400/10 px-1 rounded">COLE_O_LINK_DA_IMAGEM_AQUI</code> pelo link</li>
                  <li>Pronto! A imagem aparece no perfil ✨</li>
                </ol>
              </div>

              <div className="bg-[#161b22] border border-[#30363d] rounded-lg p-4">
                <p className="font-semibold text-white mb-2">📌 O que substituir no README:</p>
                <table className="w-full text-xs">
                  <tbody>
                    {[
                      { find: 'COLE_O_LINK_DA_IMAGEM_AQUI', what: '👋 Seu anime dando oi (igual a Marin no topo)' },
                      { find: 'COLE_O_LINK_DA_RENDER_AQUI', what: '🧊 Render do Blender (igual a do lado do código)' },
                      { find: 'COLE_LINK_RENDER_01 a 04', what: '🎨 4 imagens da galeria (igual os cosplays da Marin)' },
                    ].map((r, i) => (
                      <tr key={i} className="border-b border-[#21262d] last:border-0">
                        <td className="py-2 pr-3"><code className="text-yellow-400 bg-yellow-400/10 px-1 py-0.5 rounded text-[10px]">{r.find}</code></td>
                        <td className="py-2 text-[#8b949e]">{r.what}</td>
                      </tr>
                    ))}
                  </tbody>
                </table>
              </div>

              <div className="bg-amber-500/10 border border-amber-500/20 rounded-lg p-3 text-xs text-amber-300">
                ⚠️ <strong>Links do Discord podem expirar!</strong> Se a imagem sumir depois de um tempo, use o <a href="https://imgur.com" target="_blank" className="underline text-amber-200 hover:text-white">Imgur</a> (link permanente).
              </div>
            </div>
          </div>
        </div>
      ) : (
        <div className="max-w-5xl mx-auto px-4 py-8">
          <div className="border border-[#30363d] rounded-lg bg-[#0d1117] overflow-hidden">
            <div className="px-4 py-3 border-b border-[#30363d] bg-[#161b22] flex items-center justify-between">
              <div className="flex items-center gap-2">
                <svg width="16" height="16" viewBox="0 0 16 16" fill="#8b949e"><path d="M2 1.75C2 .784 2.784 0 3.75 0h6.586c.464 0 .909.184 1.237.513l2.914 2.914c.329.328.513.773.513 1.237v9.586A1.75 1.75 0 0 1 13.25 16h-9.5A1.75 1.75 0 0 1 2 14.25Zm1.75-.25a.25.25 0 0 0-.25.25v12.5c0 .138.112.25.25.25h9.5a.25.25 0 0 0 .25-.25V6h-2.75A1.75 1.75 0 0 1 9 4.25V1.5Zm6.75.062V4.25c0 .138.112.25.25.25h2.688l-.011-.013-2.914-2.914-.013-.011Z"></path></svg>
                <span className="text-sm text-[#c9d1d9] font-semibold">README.md</span>
                <span className="text-xs text-[#8b949e] bg-[#21262d] px-2 py-0.5 rounded-full ml-2">Raw</span>
              </div>
              <button onClick={handleCopy} className="px-3 py-1 rounded-md bg-[#21262d] hover:bg-[#30363d] text-[#c9d1d9] text-xs font-medium transition-colors border border-[#30363d]">
                {copied ? '✓ Copiado!' : '📋 Copy'}
              </button>
            </div>
            <div className="p-4 overflow-x-auto">
              <pre className="text-xs sm:text-sm font-mono text-[#c9d1d9] whitespace-pre-wrap break-all leading-relaxed">{readmeRaw}</pre>
            </div>
          </div>

          <div className="mt-8 border border-[#30363d] rounded-lg bg-[#161b22] p-6">
            <h3 className="text-lg font-semibold text-white mb-4">📋 Passo a passo</h3>
            <ol className="space-y-2 text-sm text-[#8b949e] list-none">
              {[
                <>Crie o repo <code className="bg-[#21262d] px-1.5 py-0.5 rounded text-[#c9d1d9]">afporiginal/afporiginal</code></>,
                <>Clique <strong className="text-white">"📋 Copiar README"</strong></>,
                <>Cole no <code className="bg-[#21262d] px-1.5 py-0.5 rounded text-[#c9d1d9]">README.md</code></>,
                <>Envie suas imagens no <strong className="text-white">Discord</strong> → copie os links → substitua os <code className="text-yellow-400 bg-yellow-400/10 px-1 rounded">COLE_O_LINK_...</code></>,
                <>Configure a Snake (instruções no final do README)</>,
                <>Perfil <strong className="text-purple-400">lendário</strong> 🚀</>,
              ].map((text, i) => (
                <li key={i} className="flex gap-3">
                  <span className="text-purple-400 font-bold shrink-0 font-mono">{i + 1}.</span>
                  <span>{text}</span>
                </li>
              ))}
            </ol>
          </div>
        </div>
      )}
    </div>
  );
}

export default App;
