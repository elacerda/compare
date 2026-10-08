# Estratégia de 2º turno — Centro Histórico + Fazenda do Max + Praia Comprida (São José/SC)
## Incoerências do plano de Flávio × contrapontos do plano de Lula, perfil por perfil

**Objetivo:** converter no 2º turno (25/10/2026) o voto do 1º turno
(04/10/2026) dado a Flávio Bolsonaro, nas seções da área
**Centro Histórico + Fazenda do Max + Praia Comprida** (São José/SC) —
NÚCLEO: 5 locais, 37 seções, 12.962 aptos; EXT/sensibilidade: 6 locais,
69 seções, 26.074 aptos (2026).

**Base documental (tudo verificado nos textos oficiais, com página):**
- Flávio (PL) — "Para o Brasil Vencer o Atraso", 76 págs. —
  `../../FLAVIO-BOLSONARO-PARA-O-BRASIL-VENCER-O-ATRASO.pdf`
  (sha256 `ff60b7ae45083471448af7fa0bf62bbe7ce209a1d21682b3482f142e0cb8b4f0`)
- Lula (PT) — "Diretrizes para o Programa de Transformação do Brasil",
  84 págs. — `../../Programa-Governo-LULA-2026.pdf`
  (sha256 `75e2dab7b9af27454a5c1a44c3bb0d7e0eaddbd1c355ccf1536f0d0be927e47b`)
- Dados de votação por seção (TSE 2018/2022/2026) e metodologia: esta pasta
  (README + CSV + configs + folha de revisão); dados brutos em
  `../eleicoes-{2018,2022,2026}/`.

**Fato central da verificação:** em 76 páginas, o plano de Flávio não
contém **nenhuma** ocorrência de "farmácia" (contagem exata 0, formas por
radical "—"), "genérico" (0), "insulina" (0), "medicamento" (0) nem
"salário mínimo" (0) — e o mesmo plano promete "entrega de remédio em
domicílio" (p. 38), INSS "profissional, medida por uma coisa só: quanto tempo o aposentado espera para receber" (p. 26) e "o mesmo salário
comprando mais" (p. 33). O único corte quantificado de todo o plano é
"no mínimo 10 ministérios" (p. 69). Cada ausência vira incoerência quando
o mesmo documento promete coisas a esse eleitor em outros capítulos.

---

## 1. O alvo, em números

### NÚCLEO (5 locais: IFSC Centro Histórico, EBM + CEI Fazenda do Max, EEB + Anhanguera Praia Comprida)

| Eleição | Turno | L × R | Outros | Total | Margem | Share L |
|---|---|---|---:|---:|---:|---:|
| 2018 | 1º | 862 × 5.049 | 3.102 | 9.013 | **−70,8 pp** | 14,6% |
| 2018 | 2º | 2.241 × 5.910 | 755 | 8.906 | **−45,0 pp** | 27,5% |
| 2022 | 1º | 3.309 × 4.956 | 1.437 | 9.702 | **−19,9 pp** | 40,0% |
| 2022 | 2º | 3.566 × 5.720 | 425 | 9.711 | **−23,2 pp** | 38,4% |
| 2026 | 1º | 3.206 × 5.688 | 1.495 (C 1.123 + BN 372) | 10.389 | **−27,9 pp** | 36,0% |

- **A área é swing de verdade, mas está recuando.** De −70,8 pp (2018 1ºT)
  para −19,9 pp (2022 1ºT) — o maior salto da amostra — e recuou para
  −27,9 pp em 2026. A base esquerda é real (share 36–40% desde 2022) mas a
  direita nunca perdeu a maioria.
- **O 2º turno não é automático aqui.** Em 2022 o 2º turno *aprofundou* a
  margem da direita (−19,9 → −23,2 pp; base rate medido L×1,08 / R×1,15).
  Em 2018 o 2º turno fez o swing oposto (base rate medido L×2,60) — a
  magnitude necessária **já aconteceu nesta área** (no contexto
  Bolsonaro×Haddad). O swing de 2026 tem que ser construído seção por
  seção.
- **Escola-swing: 1660 (EEB Profª Maria José Barbosa Vieira, Praia
  Comprida)** — a única do NÚCLEO perto do empate: −34,7 pp (2018 2ºT) →
  **−4,5 pp (2022 2ºT, share L 47,8%)** → −11,2 pp (2026 1ºT, 44,4%). A
  seção **1660/381 venceu a esquerda por +38 votos no 2º turno de 2022** e
  está a −9 em 2026: a seção mais virada da área — e a frase de porta a
  porta mais forte ("essa seção votou no Lula em 2022").
- **Flips 2022 → 2026 (mesmo local+seção): 4, TODOS esquerda→direita**
  (zero no sentido inverso): 1660/371, 1660/381, 1627/384, 1619/385.
  Histórico: 2018→2022 o swing foi o inverso (1660/371 D→E) — a geografia
  do swing é a mesma em ambos os sentidos.
- **7 seções próximas (|margem| ≤ 10 pp)** em 2026 1ºT: L 824 × R 892
  (−4,0 pp): 1740/390, 1708/410, 1619/392 (+3,8 — única à esquerda),
  1660/381, 1740/386, 1660/398, 1627/384. Se virassem 50×50: +68 no
  diferencial; 55×45 (teto): **+269**.
- **Matemática do 2º turno:** votos p/ virar o NÚCLEO = **2.482** — exigir
  ~24 pp de swing: **fora de alcance**; a meta é decomposta:
  - **devolver as 4 seções flipadas ao nível de 2022 1ºT: +226** (medido nos
    resultados de 2022 da mesma seção);
  - **converter as 7 seções próximas: +68 a +269** (50×50 a 55×45);
  - **pool de comparecimento: 2.945** (abstenções 2.573 + branco/nulo 372) —
    mobilizar indecisos rende sem "vencer" ninguém.
  - **Meta realista do NÚCLEO: +400 a +800 no diferencial L×R** — margem de
    −27,9 pp para **−22 a −18 pp**, share L de 36% para **39–41%**.
- **O resto (1104, 1597 no NÚCLEO; margem 25–35 pp) é manutenção de base +
  comparecimento, não conversão.**

### EXT / sensibilidade (6 locais adjacentes: Roçado, Picadas do Sul, Forquilhinha×2, Campinas×2)

| Eleição | Turno | L × R | Outros | Total | Margem | Share L |
|---|---|---|---:|---:|---:|---:|
| 2018 | 1º | 1.991 × 11.139 | 6.118 | 19.248 | −69,7 pp | 15,2% |
| 2018 | 2º | 4.637 × 12.810 | 1.630 | 19.077 | −46,8 pp | 26,6% |
| 2022 | 1º | 6.445 × 10.830 | 2.848 | 20.123 | −25,4 pp | 37,3% |
| 2022 | 2º | 6.987 × 12.445 | 746 | 20.178 | −28,1 pp | 36,0% |
| 2026 | 1º | 6.198 × 12.024 | 2.764 (C 2.065 + BN 699) | 20.986 | −32,0 pp | 34,0% |

- Votos p/ virar a EXT: **5.826** — fora de alcance; papel da EXT em 2026:
  **estancar o recuo** (share 37,3% → 34,0% em 4 anos) e **comparecimento**
  (pool de 5.787 aptos). A melhor margem da fronteira é 1619
  (Forquilhinha, −16,8 pp em 2022 2ºT; flip em 1619/385).

---

## 2. Quem votou no Flávio na área — os 7 perfis

O eleitor daqui não é "o bolsonarista de TV": votou à direita por custo de
vida, segurança e desconfiança de "politiqueiro", numa cidade que é o maior
pólo industrial da Grande Florianópolis (metalurgia/metalomecânica,
eletrônicos, plásticos) em verticalização acelerada.

1. **Comércio e serviços do Centro Histórico** — lojas, restaurantes,
   serviços do Calçadão Beira Mar e das ruas centrais (IFSC 1597 no bairro).
2. **Trabalhador industrial / metalomecânico / tecnologia** — o parque
   industrial de São José, a maior massa salarial da região.
3. **Construção civil / pedreiro** — a verticalização do eixo Beira
   Mar–centro (canteiros em toda a área).
4. **Aposentado / idoso** — os bairros residenciais de Fazenda do Max e
   Praia Comprida (1104, 1627, 1660); envelhecimento acelerado.
5. **Mulher que trabalha e cuida** — as creches/escolas do NÚCLEO (CEI
   Santo Antônio 1627, EBM Albertina Krummel 1104) marcam o perfil do
   eleitorado: filho pequeno + renda dupla.
6. **Estudante / jovem** — dois pólos no NÚCLEO: **IFSC Campus São José
   (1597)** e **Faculdade Anhanguera (1708)** — o local de votação é o
   próprio campus.
7. **Autônomo informal / ambulante** — centro e praia: serviço avulso,
   revenda, praia no fim de semana.

---

## 3. As incoerências do plano de Flávio (verificadas no texto)

### I.1 "Grande TESOURAÇO" × um plano cheio de programas novos
"Nossa bandeira é um grande TESOURAÇO: um corte profundo e por todos os
lados, que enxuga a máquina, coloca as contas em ordem e reduz os impostos
que pesam sobre quem produz" (p. 68); "corte de no mínimo 10 ministérios, a
redução de cargos comissionados e de despesas administrativas" (p. 69). No
mesmo documento: Casa Verde e Amarela "com meta de 2,5 milhões de
residências" (p. 47), "voucher-creche para acesso à rede privada
credenciada" (p. 21), "A Central da Mulher será um espaço físico" (p. 17),
"Um Tesouraço da Burocracia para integrar serviços" (p. 11). Nenhum desses
programas tem custo apresentado.
**Uso:** "o plano que promete cortar o Estado está criando um monte de
programa novo do Estado — e o único número de corte de todo o plano são 10
ministérios (p. 69). A conta desses programas é o mesmo corte que ele
promete."

### I.2 Tudo condiciona a "superávits primários" — sem um centavo de fonte
"Vamos construir o equilíbrio fiscal duradouro, entregando superávits
primários e limitando o crédito subsidiado com recursos do Tesouro" (p. 71);
a promessa central de crédito é "a menor taxa de juros possível no
financiamento" da casa própria (p. 47) — e "este capítulo é a garantia de
que tudo o que foi prometido nos anteriores tem lastro" (p. 68). O único
corte quantificado do plano inteiro é "no mínimo 10 ministérios" (p. 69).
**Contraponto Lula:** o programa nomeia fonte e número por área — "R$ 25
bilhões, com o Novo PAC, em obras de contenção de encostas e drenagem
urbana sustentável" (p. 47); "meta para 3 milhões até o final de 2026"
(MCMV, p. 45); "mais 233 km de metrôs, trens e VLTs e outros 296 km de
corredores exclusivos de ônibus no padrão BRT" (p. 46).
**Uso:** "ele promete juros menores 'quando as contas se ajeitarem' — mas o
único número de corte do plano inteiro é 10 ministérios. A conta do seu
empréstimo não é ajeitada por promessa, é ajeitada por dinheiro
apresentado. No plano do Lula cada obra tem o número dela."

### I.3 "Custo do trabalho é duas vezes o salário" × "reduzir sem retirar direitos"
"o custo de um trabalhador formal chega a cerca de duas vezes o salário que
ele leva para casa. Essa diferença é o que faz muita empresa não contratar,
ou contratar na informalidade" (p. 43) — e a solução: "Vamos reduzir
gradualmente o custo do trabalho, sem retirar direitos" (p. 43). O custo
extra que ele diagnostica é justamente o dos direitos (FGTS, 13º, INSS) —
não existe forma de baratear a folha sem mexer na contribuição, de onde saem
o FGTS e a aposentadoria do próprio trabalhador.
**Contraponto Lula:** "Emprego com proteção previdenciária, direitos
trabalhistas, remuneração justa e jornada de trabalho não exaustiva" (p. 25);
"assegurar o fim da escala 6x1 e a redução da jornada de trabalho para 40
horas, sem redução salarial" (p. 75).
**Uso (industrial/construção):** "a planilha dele diz que o registrado custa
o dobro do salário — e a solução dele é baratear o registro. Baratear o
registro é tirar do seu FGTS e da sua aposentadoria. É o contrário do que
você votou em 2018: trabalhar com garantia, não mais barato."

### I.4 "O trabalhador em primeiro lugar, não o sindicato" que defende o negociado
"O trabalhador em primeiro lugar, não o sindicato — proteger quem trabalha,
não quem vive da estrutura sindical. O país precisa se posicionar contra a
República Sindical" (p. 44) — no mesmo capítulo em que: "defendemos o
negociado sobre o legislado, ou seja, permitir que trabalhador e empresa
combinem diretamente as condições de trabalho" (p. 44), e o "jornada
flexível que caiba na vida de mães" (p. 44). O mesmo plano manda: no INSS,
"Sai a gestão voltada a entidades sindicais, entra a gestão profissional"
(p. 26).
**Contraponto Lula:** "fortalecer a negociação coletiva" e o emprego com
proteção (p. 25, 75); "buscar reestruturar a base de financiamento da
Previdência, buscando a diversidade das fontes de custeio" (p. 77).
**Uso (servidor/metalúrgico sindicalizado):** "o plano fala mal do sindicato
e depois pede pro sindicato negociar — 'o negociado sobre o legislado' é
justamente a ferramenta dele. Se o sindicato é a 'república sindical' que
atrapalha, quem negocia a sua carreira é?"

### I.5 Escolas "livres de doutrinação" e universidade trocando de dono — numa área que vota no IFSC
"A educação será orientada pelo conhecimento e livre de doutrinação
político-partidária" + "Vamos ampliar as Escolas Cívico-Militares" (p. 35)
+ "No ensino superior, vamos transferir a governança para o Ministério da
Ciência, Tecnologia e Inovações, unificando ciência e ensino superior sob o
mesmo teto" (p. 36). A área alvo tem **IFSC no NÚCLEO (1597)** e
**faculdade (1708)** — o eleitor que vota no campus federal é o primeiro
afetado por essa mudança de dono.
**Contraponto Lula:** "Fortaleceremos ainda mais a assistência estudantil,
ampliando o acesso à alimentação e à moradia estudantil para os jovens que
estão no ensino superior" (p. 24); "expansão e interiorização da educação
superior pública para superar os vazios educacionais" (p. 33).
**Uso (estudante/funcionário do IFSC):** "o plano dele tira o ensino
superior do Ministério da Educação e joga pro Ministério da Ciência — o
seu campus vira laboratório de produção. No plano do Lula o aluno tem
refeição e moradia garantidas na universidade."

### I.6 "Remédio em domicílio" × zero menção a farmácia, genérico, insulina
"um sistema de entrega de remédio em domicílio vai garantir que o idoso, a
pessoa com deficiência e o doente crônico não precisem escolher entre buscar
o tratamento e pagar o transporte" (p. 38); "A fila do INSS, que chegou a 3
milhões..." (p. 23); "Sai a gestão voltada a entidades sindicais, entra a gestão
profissional, medida por uma coisa só: quanto tempo o aposentado espera para
receber" (p. 26); "o mesmo salário comprando mais. Para o aposentado, que
vive de renda fixa e é o primeiro a sentir a alta de preços, isso é a
diferença entre chegar ao fim do mês com o remédio comprado ou..." (p. 33).
E no plano inteiro: **"farmácia" 0, "genérico" 0, "insulina" 0,
"medicamento" 0** (contagem exata = 0 e formas por radical "—"). O plano
fala do remédio do idoso sem falar do que segura o remédio dele: a farmácia.
**Contraponto Lula:** "Retomamos o Farmácia Popular, ampliando para 41 o
número de medicamentos gratuitos distribuídos. Chegamos, em 2025, a 27,3
milhões de pessoas atendidas, 32% mais que em 2022" (p. 36); "A Farmácia
Popular passou a distribuir absorventes, garantindo a dignidade menstrual de
3,3 milhões de meninas e mulheres" (p. 38); INSS: "reestruturar a base de
financiamento da Previdência" (p. 77).
**Uso (aposentado/Fazenda do Max, Praia Comprida):** "leia o plano inteiro:
'farmácia', 'insulina', 'genérico' não aparecem uma única vez — e o plano
promete entregar o remédio no seu domicílio. No plano do Lula a farmácia
tem nome e número: 41 remédios gratuitos, 27,3 milhões de pessoas
atendidas."

### I.7 Central da Mulher "espaço físico" e voucher-creche × a mulher que trabalha e cuida
"A Central da Mulher será um espaço físico onde a mulher resolve a vida sem
perder tempo nem percorrer a cidade inteira" (p. 17); "Onde não houver vaga
na rede pública, a família receberá um voucher-creche para acesso à rede
privada credenciada até a vaga pública surgir, para que nenhuma mulher deixe
de trabalhar, estudar ou empreender por falta de creche" (p. 21). Promessas
sem quantidade, sem prazo, sem dinheiro — e a creche pública vira fila até
"o voucher aparecer".
**Contraponto Lula:** "aceleramos o tempo para expedição de Medidas
Protetivas de Urgência, que caiu de 16 para 3 dias... concluiremos as 30
Casas da Mulher Brasileira e os 15 Centros de Referência da Mulher
Brasileira" (p. 21); "Cuidotecas, espaços de acolhida de crianças de 3 a 12
anos, que liberam o tempo das mulheres responsáveis pelo cuidado das
crianças" (p. 26); "O Novo PAC apoiou a construção de 3.562 creches e
escolas de educação infantil em 2.360 municípios" (p. 31).
**Uso (mãe que trabalha, porta da creche/CEI):** "o plano dele da creche é
um voucher da rede privada 'até a vaga pública surgir'. O plano do Lula
tem creche construída — 3.562 em 2.360 municípios — e Cuidoteca pra você
trabalhar sem deixar o filho com a vizinha."

### I.8 "Ônibus lotado" e drenagem — sem um número no capítulo
"Milhões de brasileiros perdem, todo dia, horas dentro de um ônibus lotado
para ir e voltar do trabalho. É tempo roubado da família, do descanso e do
estudo" (p. 51); "barragens de usos múltiplos, reservatórios de controle de
cheias, diques, canais e obras de drenagem e macrodrenagem" (p. 52). O
diagnóstico é bom; a solução não traz quilômetro, ônibus ou real.
**Contraponto Lula:** "mais 233 km de metrôs, trens e VLTs e outros 296 km
de corredores exclusivos de ônibus no padrão BRT... renovar a frota de
ônibus de 144 municípios, com a aquisição de 3.942 ônibus Euro 6, 203
ônibus elétricos" (p. 46); "R$ 25 bilhões, com o Novo PAC, em obras de
contenção de encostas e drenagem urbana sustentável" (p. 47).
**Uso (quem pega ônibus no eixo centro–Beira Mar):** "ele descreve o seu
ônibus lotado certinho — e não diz quantos ônibus nem quantos km vai fazer.
No plano do Lula o número existe: 233 km de trilho, 296 km de corredor,
3.942 ônibus novos e 25 bilhões na drenagem da sua rua."

---

## 4. Cartões 1-frase por perfil

| Perfil | Cartão (tudo com página) |
|---|---|
| Comércio do Centro | "O plano dele jura que você vai 'abrir a porta do comércio de manhã e voltar para casa à noite' (p. 13) — mas 'farmácia' e 'salário mínimo' não aparecem uma vez nas 76 páginas, e o único corte quantificado é 10 ministérios (p. 69). No do Lula: Farmácia Popular com 41 remédios gratuitos (p. 36)." |
| Industrial / metalúrgico | "O plano que diagnostica 'o trabalhador formal custa duas vezes o salário' (p. 43) e promete baratear 'sem retirar direitos' (p. 43) — baratear é tirar do seu FGTS e da sua aposentadoria. No do Lula: 'emprego com proteção previdenciária' (p. 25) e fim da escala 6x1 (p. 75)." |
| Construção civil | "O plano dele promete casa com 'a menor taxa de juros possível' (p. 47) — sem nenhum número no plano; o único corte quantificado são 10 ministérios (p. 69). No do Lula: 3 milhões de moradias do MCMV até o fim de 2026 (p. 45) e R$ 25 bi na drenagem (p. 47)." |
| Aposentado | "O plano dele mede o INSS por 'quanto tempo o aposentado espera para receber' (p. 26) e diagnostica 'a fila do INSS, que chegou a 3 milhões' (p. 23) — mas 'insulina', 'genérico' e 'farmácia' aparecem zero vezes. No do Lula: Farmácia Popular, 41 remédios gratuitos, 27,3 milhões de pessoas (p. 36) e valorização do salário mínimo (p. 74)." |
| Mulher que trabalha e cuida | "O plano dele é um 'espaço físico' (Central da Mulher, p. 17) e um voucher-creche da rede privada (p. 21). No do Lula: medida protetiva em 3 dias em vez de 16 (p. 21), Cuidoteca que 'libera o tempo das mulheres' (p. 26) e 3.562 creches construídas (p. 31)." |
| Estudante / jovem | "O plano dele escola 'livre de doutrinação' (p. 35) e ensino superior transferido pro Ministério da Ciência (p. 36) — no bairro onde o IFSC é o local de votação. No do Lula: assistência estudantil com alimentação e moradia (p. 24)." |
| Autônomo informal | "O plano que diz 'o trabalhador em primeiro lugar, não o sindicato' (p. 44) não deixa número nenhum pra você: 'salário mínimo' não aparece uma vez nas 76 páginas. No do Lula: valorização do salário mínimo 'como meio estratégico de distribuição de renda' (p. 74)." |

---

## 5. O que NÃO dizer (evitar backfire)

1. **Não atacar Bolsonaro pelo nome na porta a porta** do votante dele.
   Atacar o documento: "o plano dele" — o votante se preserva ("eu votei no
   Flávio, não é o mesmo que 2018").
2. **Não entrar no eixo institucional (STF, censura, "república sindical"
   como acusação)** — é o eixo de identidade desses eleitores; entrar nele
   reafirma a pertença. Manter a conversa 100% no bolso, na obra da rua, no
   mercado. (Citar a *frase do plano* sobre a "república sindical" como
   incoerência interna — I.4 — é diferente: é mostrar que o plano se
   contradiz, não acusar o eleitor.)
3. **Não repetir "Lula é do povo, o outro é dos ricos"** — clichê já
   rejeitado; o plano de Flávio fala a língua do pequeno negócio justamente
   pra se diferenciar. O contra-argumento é a incoerência verificada, não o
   rótulo.
4. **Não prometer o que o plano do Lula não diz** — cada frase de porta em
   porta tem que ter página; sem página, não diz.
5. **Terceiros do 1º turno puxam à direita:** no NÚCLEO a coluna C (centro)
   teve **1.123 votos** em 2026 (2.065 na EXT) — normalmente migram para a
   direita no 2º turno. Para esses, o argumento é **custo de vida puro + a
   inexistência de alternativa de centro no 2º turno**, não o plano do
   Flávio (eles não votaram nele). O split C/BN da análise existe
   exatamente para separar esse pool.

---

## 6. Alvo por seção e canal (janela 07/10 → 25/10)

- **Janela:** 19 dias. Picos: sábado/domingo manhã (Calçadão, praia,
  mercado) e fim de mês (a dor do custo de vida está no máximo).
- **Prioridade 1 — as 4 seções flipadas (2022→2026, todas E→D):**
  1660/371, 1660/381, 1627/384, 1619/385. Porta a porta de 1º grau:
  morador da própria seção falando com os vizinhos da mesma seção. Meta:
  **devolver ao nível de 2022 1ºT (+226 no diferencial, medido)**. Âncora
  de 1660/381: "essa seção votou no Lula no 2º turno de 2022 e venceu por
  38 votos".
- **Prioridade 2 — as 7 seções próximas (|margem| ≤ 10 pp):** 1740/390,
  1708/410, 1619/392, 1660/381, 1740/386, 1660/398, 1627/384 (agregado
  L 824 × R 892). Meta: **50×50 (+68) a 55×45 (+269)**. 1619/392 já está à
  esquerda (+3,8) — semente de boca a boca.
- **Prioridade 3 — escolas-swing:** 1660 (Praia Comprida — 5 seções, share
  44,4%; a escola do swing), 1708 (Anhanguera — 43,4%, local novo de
  estudante), 1597 (IFSC — 35,2%; campus). Rodas de conversa nos próprios
  locais de votação (o eleitor já transita por eles).
- **Base (manutenção, não conversão):** 1104 e 1627 (Fazenda do Max,
  margem 30–35 pp) e toda a EXT (1066, 1260, 1422, 1619, 1511, 1740;
  margem 20–38 pp) — manter o share (~32–40%) e o comparecimento (pool de
  2.945 no NÚCLEO, 5.787 na EXT).
- **Canais por perfil:**
  - Comércio do Centro: roda rápida de 10 min na abertura (antes das 9h),
    Calçadão Beira Mar e ruas centrais; 1 cartão A5 por perfil.
  - Estudante/jovem: portões do **IFSC (1597)** e da **Anhanguera (1708)**
    no fim de turma/entrada de aula — o local de votação é o campus.
  - Construção: canteiro no intervalo do almoço, eixo Beira Mar–centro — o
    argumento FGTS/registro (I.3) é o único que funciona com pedreiro.
  - Industrial/metalúrgico: troca de turno (chegada/saída) nos portões do
    parque industrial, nos bairros de moradia (Forquilhinha, Roçado,
    Campinas).
  - Aposentado: fila do INSS, centros comunitários e ruas residenciais de
    Fazenda do Max e Praia Comprida, fim de tarde.
  - Mulher que cuida: **portão da creche/CEI (1627, 1104) no horário de
    busca (16h–18h)** — o argumento creche/Cuidoteca (I.7) é o que abre a
    conversa.
  - Autônomo informal: calçadão da praia e mercado de sábado.
- **Mensagem de fechamento universal:** "nas 76 páginas do plano dele, as
  palavras 'farmácia', 'insulina' e 'salário mínimo' não aparecem. Não é
  que ele seja contra você — é que você não está no plano dele. O outro
  plano nomeia: 41 remédios gratuitos, R$ 25 bilhões na drenagem da sua
  rua, 3 milhões de casas."

---

## 7. Limites desta análise

- Citações verificadas nos PDFs oficiais (sha256 acima); páginas conforme
  numeração do PDF. A qualificação de "incoerência" é **interpretação
  estratégica do documento, não juízo sobre a boa-fé do candidato**.
  Declarações do plano (ex.: "3.562 creches", "27,3 milhões atendidas")
  são **alegações dos documentos**, não fatos auditados.
- Toda lacuna ("não aparece no plano") tem contagem exata = 0 **e** formas
  por radical "—" no texto extraído inteiro (farmácia, genérico, insulina,
  medicamento, salário mínimo — no plano de Flávio).
- Dados de seção: `detalhe_por_secao.csv`
  (480 linhas) — metodologia, revisão de geocodificação (folha arquivada) e
  validação (T == QT_COMPARECIMENTO OK, 480 seções; aptos ≥ T OK) no README
  da pasta.
- **Seções são renumeradas a cada eleição** — flips por mesmo local +
  mesmo nº de seção; cobertura de matching declarada (2018×2022: 100%;
  2022×2026: 97%); todo flip é estrito (código), zero por nome.
- **2026 não tem 2º turno ainda** — os cenários de 2º turno são previsão
  (hipóteses declaradas), exceto os base rates 2018/2022, que são medidos.
  O 2º turno = crossover + comparecimento dos indecisos (pool 2.945 no
  NÚCLEO), **não migração total** do voto Flávio.
- Geocodificação revisada local por local (folha em
  `geocode.tsv.folha.tsv`); **"Fazenda do Max" ≈
  "Fazenda Santo Antônio" é inferência declarada** (Wikipedia: terras de
  Max Habitzel); 7 locais sem resultado no OSM foram excluídos (nenhum tem
  seção em 2018/2022/2026 — zero impacto); 1708/1740 são locais novos
  (somente 2026).
- A seção acompanha a **escola** (local de votação), não o domicílio do
  eleitor — limitação aceita e declarada.
- **Calibração pós-2º turno:** reabrir após 25/10/2026 (baixar o 2T,
  rerodar 03/04/05, comparar realizado × cenários e flips 1T→2T por seção).
