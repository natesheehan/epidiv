<script>
  // Default to 2025/2026

    import Header from "$lib/components/Header.svelte";
    import Footer from "$lib/components/Footer.svelte"; 

  let active = '2025/2026';

  // NEW: 2025/2026 schedule
  const sessions_2526 = [
    {
      date: '19/09/2025',
      theme: 'Local and global epistemologies',
      readings: [
        { title: 'Büter, Anke. 2010. “Social Objectivity and the Problem of Local Epistemologies.” Analyse & Kritik 32(2): 213–30.', url: 'https://doi.org/10.1515/auk-2010-0202' },
        { title: 'Longino, Helen E. 2002. “Pluralism and Local Epistemologies” in The Fate of Knowledge. Princeton: Princeton University Press, pp. 175–202.' },
        { title: 'Ludwig, David. 2021. “Introduction: Reimagining Epistemology and Philosophy of Science from a Global Perspective.” In Global Epistemologies and Philosophies of Science. Routledge.' }
      ],
      background: [
        { title: 'El-Hani, C. N., Poliseli, L., & Ludwig, D. (2022). Beyond the divide… Studies in History and Philosophy of Science 91: 296–306.', url: 'https://doi.org/10.1016/j.shpsa.2021.11.004' }
      ],
      media: [
        { title: 'Leunig — Globalisation (cartoon)', url: 'https://www.leunig.com.au/works/recent-cartoons/495-globalisation' }
      ]
    },
    {
      date: '03/10/2025',
      theme: 'Butterflies, Jaguars, & Shamanism: Political and Ontological Challenges of Diversity',
      readings: [
        { title: 'Langdon, Esther J. (2016). “The performance of diversity: shamanism as a performative mode.” GIS Gesture, Image and Sound. Journal of Anthropology 1(1): 9–39.' },
        { title: 'Makovec, D. (2023/2024). Entirely Different Kinds of Beast… Philosophy of the Social Sciences 54(4): 327–353.', url: 'https://doi.org/10.1177/00483931231216773' }
      ],
      background: [
        { title: 'Rowett, Catherine. 2025. Being, becoming, and transforming: A discussion of Of jaguars and butterflies. HAU 15(2): 466–470.' }
      ],
      media: [
        { title: 'SIONA: De-mining Sacred Space in the Amazon (video)', url: 'https://www.newyorker.com/video/watch/the-effort-to-de-mine-sacred-space-in-the-amazon' }
      ]
    },
    {
      date: '17/10/2025',
      theme: 'Scientific Disagreement',
      readings: [
        { title: 'Cocchiaro, M.Z., Trpin, B. 2025. The puzzle of scientific disagreement. EJPS 15: 35.', url: 'https://doi.org/10.1007/s13194-025-00662-4' },
        { title: 'Cruz, H. De, & De Smedt, J. 2013. The Value of Epistemic Disagreement… SHPS A 44(2): 169–177.', url: 'https://doi.org/10.1016/j.shpsa.2013.02.002' }
      ],
      background: [
        { title: 'Šešelja, D. 2021. Some lessons from simulations of scientific disagreements. Synthese 198(Suppl 25): 6143–6158.', url: 'https://doi.org/10.1007/s11229-019-02182-0' }
      ],
      media: [
        { title: 'Find a debate…' }
      ]
    },
    {
      date: '31/10/2025',
      theme: 'Pluralism',
      readings: [
        { title: 'Chang, Hasok. 2012. [pick a chapter] Is Water H2O? Evidence, Realism and Pluralism. Springer.' },
        { title: 'Stengers, I. 2011. “Comparison as a Matter of Concern.” Common Knowledge 17(1): 48–63.', url: 'https://muse.jhu.edu/article/418671' },
        { title: 'Mitchell, Sandra D. 2003. Biological Complexity and Integrative Pluralism. CUP.' }
      ],
      background: [],
      media: [
        { title: 'Krauss, Rosalind. “Sculpture in the Expanded Field.” October 8 (1979): 31–44.', url: 'https://doi.org/10.2307/778224' }
      ]
    },
    {
      date: '14/11/2025',
      theme: 'What sorts of diversity?',
      readings: [
        { title: 'Solomon, Miriam. 2006. “Norms of Epistemic Diversity.” Episteme 3(1): 23–36.', url: 'https://doi.org/10.1353/epi.0.0007' },
        { title: 'Jeong, Tay. 2024. “Epistemic Diversity and Epistemic Advantage…” Hypatia 39(1): 97–117.', url: 'https://doi.org/10.1017/hyp.2023.106' },
        { title: 'Stirling, A. 2007. A general framework for analysing diversity in STS. JR Soc Interface 4(15):707–19.', url: 'https://doi.org/10.1098/rsif.2007.0213' }
      ],
      background: [
        { title: 'Franco, M. P. V., et al. 2022. “Diversity regained…” Science of the Total Environment 825: 154029.', url: 'https://www.sciencedirect.com/science/article/pii/S0048969722011214' }
      ],
      media: []
    },
    {
      date: '28/11/2025',
      theme: 'Diverse Perspectives on AI',
      readings: [
        { title: 'van Rooij, I., Guest, O., Adolfi, F. et al. 2024. Reclaiming AI as a Theoretical Tool… CBB 7: 616–636.', url: 'https://doi.org/10.1007/s42113-024-00217-5' },
        { title: 'Lewis, J.E., Whaanga, H. & Yolgörmez, C. 2025. Abundant intelligences… AI & Society 40: 2141–2157.', url: 'https://doi.org/10.1007/s00146-024-02099-4' },
        { title: 'Leonelli, S. 2025. Environmental Intelligence… Harvard Data Science Review.', url: 'https://doi.org/10.1162/99608f92.ac7c1504' }
      ],
      background: [],
      media: [
        { title: 'Joan Slonczewski — “Microbe” (novel info)', url: 'https://www.davidmswitzer.com/slonczewski/microbe2.html' }
      ]
    },
    {
      date: '12/12/2025',
      theme: 'Epistemic Injustice and Social Justice',
      readings: [
        { title: 'Ludwig, D. 2025. “It’s a Shame That You Can’t Afford Rent…” Social Epistemology.', url: 'https://www.tandfonline.com/doi/full/10.1080/02691728.2025.2472783' },
        { title: 'Bufkin, S. 2024. “Racism, epistemic injustice, and ideology critique.”', url: 'https://journals.sagepub.com/doi/10.1177/01914537241244824' },
        { title: 'Anderson, E. 2012. “Epistemic Justice as a Virtue of Social Institutions.”', url: 'https://www.tandfonline.com/doi/full/10.1080/02691728.2011.652211' }
      ],
      background: [
        { title: 'Cummings, S., Dhewa, C., Kemboi, G., & Young, S. 2023. Doing Epistemic Justice in Sustainable Development. Sustainable Development 31(3): 1965–77.', url: 'https://doi.org/10.1002/sd.2497' }
      ],
      media: []
    },
    // --- Winter break ---
    {
      date: '30/01/2026',
      theme: 'Hermeneutical injustice',
      readings: [
        { title: 'Arianna Falbo: Hermeneutical Injustice: Distortion and Conceptual Aptness | Hypatia | Cambridge Core' },
        { title: 'Paulina Sliwa: Making sense of things: Moral inquiry as hermeneutical inquiry (2024).' , url: 'https://onlinelibrary.wiley.com/doi/full/10.1111/phpr.12941' },
        { title: 'Coliva, A. 2024. Hysteria, Hermeneutical Injustice and Conceptual Engineering. Social Epistemology 39(2): 121–133.', url: 'https://doi.org/10.1080/02691728.2024.2400089' }
      ],
      background: [
        { title: 'Nicole Dular: One Too Many: Hermeneutical Excess as Hermeneutical Injustice | Hypatia | Cambridge Core' },
        { title: 'Anderson, Ellie. 2023. “Hermeneutic Labor…” Hypatia 38(1): 177–97.', url: 'https://doi.org/10.1017/hyp.2023.11' }
      ],
      media: [
        { title: 'Optional film: Witches (MUBI)', url: 'https://mubi.com/en/gb/films/witches' }
      ]
    },
    {
      date: '13/02/2026',
      theme: 'Education',
      readings: [
        { title: 'Siegel, H. 2006. Epistemological Diversity and Education Research: Much Ado About Nothing Much? Educational Researcher 35(2): 3–12.', url: 'https://doi.org/10.3102/0013189X035002003' },
        { title: 'Horsthemke, K. 2021. Diversity and Epistemic Marginalisation… Studies in Philosophy and Education 40(6): 549–65.', url: 'https://doi.org/10.1007/s11217-021-09764-x' },
        { title: 'Omodan, B. I. 2024. The Roles of Epistemology and Decoloniality… Globalisation, Societies and Education.', url: 'https://doi.org/10.1080/14767724.2024.2335661' }
      ],
      background: [],
      media: []
    },
    {
      date: '27/02/2026',
      theme: 'Diversity, Policy Making & Uncertainty',
      readings: [
        { title: 'Brugnach, M., Dewulf, A., Pahl-Wostl, C., & Taillieu, T. 2008. Toward a Relational Concept of Uncertainty. Ecology and Society 13(2).', url: 'http://www.jstor.org/stable/26267972' },
        { title: 'Honnacker, A. 2023. Beyond Evidence: Experimental Policy-Making in Uncertain Times. Inquiry.', url: 'https://doi.org/10.1080/0020174X.2023.2203162' }
      ],
      background: [
        { title: 'Kim, M. H., & Dankel, D. J. 2025. Are We Ready to Be Wrong? Futures 166: 103520.', url: 'https://doi.org/10.1016/j.futures.2024.103520' },
        { title: 'Guerrero Mc Manus, S. 2025. Dismantling Science, Dismantling Human Rights… Tapuya 8(1).', url: 'https://doi.org/10.1080/25729861.2025.2469405' }
      ],
      media: []
    },
    {
      date: '13/03/2026',
      theme: 'Open Science Practices and Movements',
      readings: [
        { title: 'Garzino Demo, L. 2025. “Preregistration Is Not a Ceiling: But It Can Become One.” Synthese 205(3): 126.', url: 'https://doi.org/10.1007/s11229-024-04828-0' },
        { title: 'Elliott, S., & Sterner, B. 2025. How Open Science Organizations Generate Epistemic Oppression. EJPS 15(3): 47.', url: 'https://doi.org/10.1007/s13194-025-00674-0' },
        { title: 'Peterson, D., & Panofsky, A. 2023. Metascience as a Scientific Social Movement. Minerva 61(2): 147–74.', url: 'https://doi.org/10.1007/s11024-023-09490-3' }
      ],
      background: [
        { title: 'Mattern, Shannon. 2023. Reparative Redaction. Library Stack.', url: 'https://www.librarystack.org/reparative-redaction/' },
        { title: 'Mattern, Shannon. 2015. “Middlewhere: Landscapes of Library Logistics.” Urban Omnibus.' }
      ],
      media: []
    }
  ];

  const sessions_2425 = [
    {
      date: '19/07/2024',
      theme: 'Introducing feminist and postcolonial philosophy of science',
      readings: [
        {
          title: 'Intemann, Kristen. 2010. “25 Years of Feminist Empiricism and Standpoint Theory: Where Are We Now?” Hypatia 25(4): 778–96.',
          url: 'https://doi.org/10.1111/j.1527-2001.2010.01138.x'
        },
        {
          title: 'Seth, Suman. 2009. “Putting Knowledge in Its Place: Science, Colonialism, and the Postcolonial.” Postcolonial Studies 12(4): 373–88.',
          url: 'https://doi.org/10.1080/13688790903350633'
        }
      ],
      background: [
        {
          title: 'Wylie, Alison. 2006. “Introduction: When Difference Makes a Difference.” Episteme 3(1–2): 1–7.',
          url: 'https://doi.org/10.3366/epi.2006.3.1-2.1'
        },
        {
          title: 'Haraway, Donna J. 1988. “Situated Knowledges…” Feminist Studies 14(3): 575.',
          url: 'https://doi.org/10.2307/3178066'
        }
      ],
      media: [
        { title: 'Ursula K. Le Guin — The Carrier Bag Theory of Fiction' },
        { title: 'Anti-Colonial Science with Max Liboiron' }
      ]
    },
    {
      date: '02/08/2024',
      theme: 'Two classical theories: Strong objectivity and well-ordered science',
      readings: [
        { title: 'Harding, Sandra. Objectivity and Diversity (2015), Ch. 2 “Stronger Objectivity for Sciences from Below”.' },
        { title: 'Kitcher, Philip. Science, Truth, and Democracy (2001), Chs. 9–10 “Organizing Inquiry”, “Well-Ordered Science”.' }
      ],
      background: [],
      media: [
        { title: 'Poems by George Oppen' },
        { title: 'Poems by Makhosazana Xaba' }
      ]
    },
    {
      date: '16/08/2024',
      theme: 'Epistemic justice and injustice in science',
      readings: [
        { title: 'Irzik & Kurtulmus. 2021. “Distributive Epistemic Justice in Science.” BJPS.', url: 'https://doi.org/10.1086/715351' },
        { title: 'Koskinen & Rolin. 2019. “SIMs Remedying Epistemic Injustice…” Phil Sci 86(5).', url: 'https://doi.org/10.1086/705522' },
        { title: 'Bagwala, A. 2024. “On informational injustice and epistemic exclusions.” Synthese.', url: 'https://doi.org/10.1007/s11229-024-04636-6' }
      ],
      background: [
        { title: 'Fricker, Miranda. 2007. Epistemic Injustice. OUP.', url: 'https://doi.org/10.1093/acprof:oso/9780198237907.001.0001' }
      ],
      media: [
        { title: 'Ex-Pajé (Ex-Shaman), Luiz Bolognesi' },
        { title: 'Octavia Butler — “The Evening and the Morning and the Night”' }
      ]
    },
    {
      date: '30/08/2024',
      theme: 'Extractivism',
      readings: [
        { title: 'Alcoff, Linda Martín. 2022. “Extractivist Epistemologies.” Tapuya.', url: 'https://doi.org/10.1080/25729861.2022.2127231' },
        { title: 'Landström, Karl. 2024. “On Epistemic Extractivism…” Phil of the Social Sciences.', url: 'https://doi.org/10.1177/00483931241255253' }
      ],
      background: [],
      media: [
        { title: 'Hija de la Laguna (Daughter of the Lake), Ernesto Cabellos' },
        { title: 'Sanaz Sohrabi — One Image, Two Acts' }
      ]
    },
    {
      date: '13/09/2024',
      theme: 'Epistemic oppression',
      readings: [
        { title: 'Thani & Anderson. 2020. “Third-Order Epistemic Exclusion…” Symposion.', url: 'https://doi.org/10.5840/symposion20207211' },
        { title: 'Subramaniam, Banu. 2014. Ghost Stories for Darwin, Ch. 7.' },
        { title: 'Pohlhaus Jr., Gaile. 2020. “Epistemic Agency Under Oppression.” Philosophical Papers.', url: 'https://doi.org/10.1080/05568641.2020.1780149' }
      ],
      background: [
        { title: 'Dotson, Kristie. 2014. “Conceptualizing Epistemic Oppression.” Social Epistemology.', url: 'https://doi.org/10.1080/02691728.2013.782585' }
      ],
      media: [
        { title: 'Remedios Varo — Mujer saliendo del psicoanalista (and more works)' }
      ]
    },
    {
      date: '27/09/2024',
      theme: 'Some benefits of diversity in epistemic communities',
      readings: [
        { title: 'Fehr, Carla. 2011. “What Is in It for Me?” in Feminist Epistemology and Philosophy of Science.' },
        { title: 'Steel, Fazelpour, Crewe, Gillette. 2021. Synthese.', url: 'https://doi.org/10.1007/s11229-019-02108-w' },
        { title: 'McBrayer, J.P. 2024. Acta Anal.', url: 'https://doi.org/10.1007/s12136-023-00582-z' }
      ],
      background: [],
      media: [
        { title: 'Donna Haraway — Story Telling For Earthly Survival' },
        { title: 'Paintings of Emily Kame Kngwarreye' }
      ]
    },
    {
      date: '11/10/2024',
      theme: 'Modeling diversity',
      readings: [
        { title: 'Zollman, K.J.S. 2010. Erkenntnis 72, 17–35.', url: 'https://doi.org/10.1007/s10670-009-9194-6' },
        { title: 'Wu, J. 2023. Philosophy of Science.', url: 'https://doi.org/10.1017/psa.2023.129' },
        { title: 'Reijula & Kuorikoski. 2021. Philosophy of Science 88(5).', url: 'https://doi.org/10.1086/714938' }
      ],
      background: [],
      media: []
    },
    {
      date: '25/10/2024',
      theme: 'Epistemic exploitation and liberatory epistemology',
      readings: [
        { title: 'Grasswick, Heidi E. 2011. “Liberatory Epistemology…”.', url: 'https://doi.org/10.1007/978-1-4020-6835-5_12' },
        { title: 'Fehr, Carla & Jones, Janet Minji. 2022. Synthese 200(6):465.', url: 'https://doi.org/10.1007/s11229-022-03787-8' },
        { title: 'Ndlovu-Gatsheni, Sabelo. 2018. Epistemic Freedom in Africa. (Open chapter)', url: 'https://library.oapen.org/bitstream/handle/20.500.12657/41376/9781138588578_oachapter1.pdf?sequence=1&isAllowed=y' }
      ],
      background: [
        { title: 'Davis, Emmalon. 2016. “Typecasts, Tokens, and Spokespersons…” Hypatia 31(3).', url: 'https://doi.org/10.1111/hypa.12251' }
      ],
      media: [
        { title: 'The Future is our Territories' },
        { title: 'Legacy Russell — Glitch Feminism (Chs. 10–11)' }
      ]
    },
    {
      date: '08/11/2024',
      theme: 'Diversity, Disadvantage and Open Science',
      readings: [
        { title: 'Dunbar-Hester, C. 2020. Hacking Diversity, ch. “Crafting and Critique…”.', url: 'https://doi.org/10.2307/j.ctvhrd181.8' },
        { title: 'Leonelli, S. 2022. “Open Science and Epistemic Diversity: Friends or Foes?”', url: 'https://doi.org/10.1017/psa.2022.45' },
        { title: 'Goldstein, R.B. 2022. “Epistemic Disadvantage.” Philosophia 50.', url: 'https://doi.org/10.1007/s11406-021-00465-w' }
      ],
      background: [],
      media: [
        { title: 'Mindy Seu — Cyberfeminism Index' },
        { title: 'Forensic Architecture' }
      ]
    },
    {
      date: '29/11/2024',
      theme: 'Linguistic Justice',
      readings: [
        { title: 'Catala, A. 2022. Journal of Political Philosophy.', url: 'https://doi.org/10.1111/jopp.12259' },
        { title: 'Peters, U. 2024. Philosophical Psychology 37(6).', url: 'https://doi.org/10.1080/09515089.2023.2261976' }
      ],
      background: [
        { title: 'Finocchiaro & Perrine. 2024. Philosophical Psychology 37(6).', url: 'https://doi.org/10.1080/09515089.2023.2284243' }
      ],
      media: []
    },
    // 2025 (still in the 2024/2025 academic year)
    {
      date: '07/02/2025',
      theme: 'Diversity of values in science',
      readings: [
        { title: 'Longino, Helen E. 1996.', url: 'https://doi.org/10.1007/978-94-009-1742-2_3' },
        { title: 'ChoGlueck, Christopher. 2022. Hypatia 37(2).', url: 'https://doi.org/10.1017/hyp.2022.11' },
        { title: 'Carrier, Martin. 2013. Science & Education 22(10).', url: 'https://doi.org/10.1007/s11191-012-9481-5' }
      ],
      background: [],
      media: []
    },
    {
      date: '28/02/2025',
      theme: 'Multiculturalism and diversity work in academia',
      readings: [
        { title: 'Massimi, Michela. 2022. Perspectival Realism, “Multiculturalism and cosmopolitanism in science”.' },
        { title: 'Ahmed, Sara. 2017. Living a Feminist Life.', url: 'https://doi.org/10.1215/9780822373377' },
        { title: 'Koskinen, Inkeri & Ludwig, David. 2021. In Global Epistemologies and Philosophies of Science.' }
      ],
      background: [],
      media: [
        { title: 'https://feministkilljoys.com/' },
        { title: 'Diversity Work (podcast)' }
      ]
    },
    {
      date: '14/03/2025',
      theme: 'Creativity',
      readings: [
        { title: 'Kidd, Ian James. 2020. EJPS 11(1):15.', url: 'https://doi.org/10.1007/s13194-020-00334-5' },
        { title: 'Anscomb, Claire. 2020. EJPS 11(1):5.', url: 'https://doi.org/10.1007/s13194-020-00310-z' },
        { title: 'Lee, Clarissa Ai Ling. 2019. Foundations of Science 24(4).', url: 'https://doi.org/10.1007/s10699-019-09615-6' }
      ],
      background: [
        { title: 'Currie, Adrian. 2019. SHPS A 76.', url: 'https://doi.org/10.1016/j.shpsa.2018.09.008' },
        { title: 'Feyerabend, Paul. 1993. Against Method.' }
      ],
      media: []
    },
    {
      date: '28/03/2025',
      theme: 'Epistemologies of Ignorance',
      readings: [
        { title: 'Tuana, Nancy. 2006. Hypatia 21(3):1–19.', url: 'https://doi.org/10.1111/j.1527-2001.2006.tb01110.x' },
        { title: 'Schiebinger, Londa. 2004. Plants and Empire — Chs 3–4 or Conclusion.' }
      ],
      background: [
        { title: 'Ortega, Mariana. 2006. Hypatia 21(3): 56–74.' },
        { title: 'Mills, Charles. 2007. In Race and Epistemologies of Ignorance.' }
      ],
      media: [
        { title: 'Our Bodies Ourselves — Online resource', url: 'https://ourbodiesourselves.org/' }
      ]
    },
    {
      date: '11/04/2025',
      theme: 'Digital Colonialism and Epistemic Injustice',
      readings: [
        { title: 'Patin et al. 2021. JASIST 72(10).', url: 'https://doi.org/10.1002/asi.24479' },
        { title: 'Gebru & Torres. 2024. First Monday 29(4).', url: 'https://doi.org/10.5210/fm.v29i4.13636' },
        { title: 'Mwema & Birhane. 2024. First Monday 29(4).', url: 'https://doi.org/10.5210/fm.v29i4.13637' }
      ],
      background: [],
      media: [
        { title: 'The Unknown Women of Content Moderation (Zine)', url: 'https://data-workers.org/ranta/' },
        { title: 'Gigwork: Manchester (Zine)', url: 'https://gigwork.city/02.%20Manchester.pdf' }
      ]
    },
    {
      date: '25/04/2025',
      theme: 'Funding',
      readings: [
        { title: 'Garrido Wainer et al. 2022. SHPS 96:68–76.', url: 'https://doi.org/10.1016/j.shpsa.2022.09.006' },
        { title: 'Sakamoto, Takahiro. 2023. Philosophy of Science 90(3).', url: 'https://doi.org/10.1017/psa.2023.49' },
        { title: 'Santana, Carlos. 2022. SHPS 92:20–26.', url: 'https://doi.org/10.1016/j.shpsa.2022.01.012' }
      ],
      background: [
        { title: 'Avin, Shahar. 2019. SHPS A 76:13–23.', url: 'https://doi.org/10.1016/j.shpsa.2018.11.006' },
        { title: 'Stengers, Isabelle. 2018. Another Science Is Possible.' }
      ],
      media: []
    },
    {
      date: '09/05/2025',
      theme: 'Choose your adventure',
      readings: [
        { title: 'Pick a chapter from: Epistemic Injustice and Violence (transcript Verlag, 2024).', url: 'https://doi.org/10.1515/9783839474389' }
      ],
      background: [],
      media: []
    },
    {
      date: '23/05/2025',
      theme: 'Debating diversity',
      readings: [
        { title: 'Cartwright, Nancy. 2021. Synthese 199(5–6).', url: 'https://doi.org/10.1007/s11229-021-03368-1' },
        { title: 'Lari, Teemu & Mäki, Uskali. 2024. Philosophy of the Social Sciences 54(5).', url: 'https://doi.org/10.1177/00483931241255230' }
      ],
      background: [],
      media: [
        { title: 'Chomsky vs Foucault (debate, video)', url: 'https://youtu.be/3wfNl2L0Gf8?si=MMlut12p7xblc3jF' }
      ]
    },
    {
      date: '06/06/2025',
      theme: 'Division of Epistemic Labour',
      readings: [
        { title: 'Thoma, J. 2015. Philosophy of Science 82.3: 454–472.', url: 'https://doi.org/10.1086/681768' },
        { title: 'Mößner, Nicola. 2022. Axiomathes 32(3): 853–70.', url: 'https://doi.org/10.1007/s10516-022-09638-y' }
      ],
      background: [
        { title: 'Solomon, Miriam. 2001. Social Empiricism.' }
      ],
      media: []
    },
    {
      date: '20/06/2025',
      theme: 'Publications and replications',
      readings: [
        { title: 'Alcalay, Rena & Vanderkerckhove, Joachim. Manuscript (2025). “Extractivism and Epistemic Disadvantage…”' },
        { title: 'Davis-Stober et al. 2025. PNAS 122(5): e2401236121.', url: 'https://doi.org/10.1073/pnas.2401236121' }
      ],
      background: [],
      media: []
    }
  ];

  function openLink(url) {
    if (!url) return;
    window.open(url, '_blank', 'noopener,noreferrer');
  }
</script>

<svelte:head>
  <link href="https://fonts.googleapis.com/css2?family=Space+Grotesk:wght@400;600&display=swap" rel="stylesheet">
</svelte:head>

<Header/>

<section class="min-h-screen bg-white text-neutral-900 font-[Space_Grotesk]">
  <!-- Toggle -->
  <div class="max-w-6xl mx-auto px-4 pt-10 pb-6">
    <div class="inline-flex rounded-full border border-neutral-200 overflow-hidden">
      <button
        class="px-4 sm:px-6 py-2 text-sm sm:text-base transition"
        class:!bg-neutral-900={active === '2024/2025'}
        class:!text-white={active === '2024/2025'}
        on:click={() => active = '2024/2025'}
        aria-pressed={active === '2024/2025'}
      >
        2024/2025
      </button>
      <button
        class="px-4 sm:px-6 py-2 text-sm sm:text-base transition border-l border-neutral-200"
        class:!bg-neutral-900={active === '2025/2026'}
        class:!text-white={active === '2025/2026'}
        on:click={() => active = '2025/2026'}
        aria-pressed={active === '2025/2026'}
      >
        2025/2026
      </button>
    </div>
  </div>

  <!-- Content -->
  <div class="max-w-6xl mx-auto px-4 pb-16">
    {#if active === '2025/2026'}
  <!-- Mobile: cards -->
  <div class="grid gap-4 md:hidden">
    {#each sessions_2526 as s}
      <article class="rounded-xl border border-neutral-200 p-4">
        <div class="flex items-baseline justify-between gap-3">
          <h3 class="font-semibold">{s.theme}</h3>
          <span class="text-xs px-2 py-1 rounded-full bg-neutral-100">{s.date}</span>
        </div>

        {#if s.readings?.length}
          <div class="mt-3">
            <h4 class="text-sm font-medium text-neutral-600">Readings</h4>
            <ul class="mt-1 space-y-1 text-sm leading-snug">
              {#each s.readings as r}
                <li>
                  {#if r.url}
                    <a href={r.url} target="_blank" rel="noopener noreferrer" class="underline underline-offset-2 hover:text-blue-700">{r.title}</a>
                  {:else}
                    {r.title}
                  {/if}
                </li>
              {/each}
            </ul>
          </div>
        {/if}

        {#if s.background?.length}
          <div class="mt-3">
            <h4 class="text-sm font-medium text-neutral-600">Supplementary reading</h4>
            <ul class="mt-1 space-y-1 text-sm leading-snug">
              {#each s.background as r}
                <li>
                  {#if r.url}
                    <a href={r.url} target="_blank" rel="noopener noreferrer" class="underline underline-offset-2 hover:text-blue-700">{r.title}</a>
                  {:else}
                    {r.title}
                  {/if}
                </li>
              {/each}
            </ul>
          </div>
        {/if}

        {#if s.media?.length}
          <div class="mt-3">
            <h4 class="text-sm font-medium text-neutral-600">Optional Art/Media</h4>
            <ul class="mt-1 space-y-1 text-sm leading-snug">
              {#each s.media as r}
                <li>
                  {#if r.url}
                    <a href={r.url} target="_blank" rel="noopener noreferrer" class="underline underline-offset-2 hover:text-blue-700">{r.title}</a>
                  {:else}
                    {r.title}
                  {/if}
                </li>
              {/each}
            </ul>
          </div>
        {/if}
      </article>
    {/each}
  </div>

  <!-- Desktop: table -->
  <div class="hidden md:block overflow-x-auto rounded-xl border border-neutral-200">
    <table class="w-full text-left text-sm">
      <thead class="bg-neutral-50 text-neutral-600">
        <tr>
          <th class="px-4 py-3 w-32">Date</th>
          <th class="px-4 py-3 w-80">Theme</th>
          <th class="px-4 py-3">Readings</th>
          <th class="px-4 py-3">Supplementary</th>
          <th class="px-4 py-3">Optional Art/Media</th>
        </tr>
      </thead>
      <tbody>
        {#each sessions_2526 as s, i}
          <tr class={i % 2 ? 'bg-white' : 'bg-neutral-50/40'}>
            <td class="align-top px-4 py-3 whitespace-nowrap text-neutral-700">{s.date}</td>
            <td class="align-top px-4 py-3 font-semibold">{s.theme}</td>
            <td class="align-top px-4 py-3">
              {#if s.readings?.length}
                <ul class="list-disc pl-5 space-y-1">
                  {#each s.readings as r}
                    <li>
                      {#if r.url}
                        <a href={r.url} target="_blank" rel="noopener noreferrer" class="underline underline-offset-2 hover:text-blue-700">{r.title}</a>
                      {:else}
                        {r.title}
                      {/if}
                    </li>
                  {/each}
                </ul>
              {/if}
            </td>
            <td class="align-top px-4 py-3">
              {#if s.background?.length}
                <ul class="list-disc pl-5 space-y-1">
                  {#each s.background as r}
                    <li>
                      {#if r.url}
                        <a href={r.url} target="_blank" rel="noopener noreferrer" class="underline underline-offset-2 hover:text-blue-700">{r.title}</a>
                      {:else}
                        {r.title}
                      {/if}
                    </li>
                  {/each}
                </ul>
              {/if}
            </td>
            <td class="align-top px-4 py-3">
              {#if s.media?.length}
                <ul class="list-disc pl-5 space-y-1">
                  {#each s.media as r}
                    <li>
                      {#if r.url}
                        <a href={r.url} target="_blank" rel="noopener noreferrer" class="underline underline-offset-2 hover:text-blue-700">{r.title}</a>
                      {:else}
                        {r.title}
                      {/if}
                    </li>
                  {/each}
                </ul>
              {/if}
            </td>
          </tr>
        {/each}
      </tbody>
    </table>
  </div>
{:else}
      <!-- Mobile: cards -->
      <div class="grid gap-4 md:hidden">
        {#each sessions_2425 as s}
          <article class="rounded-xl border border-neutral-200 p-4">
            <div class="flex items-baseline justify-between gap-3">
              <h3 class="font-semibold">{s.theme}</h3>
              <span class="text-xs px-2 py-1 rounded-full bg-neutral-100">{s.date}</span>
            </div>

            {#if s.readings?.length}
              <div class="mt-3">
                <h4 class="text-sm font-medium text-neutral-600">Readings</h4>
                <ul class="mt-1 space-y-1 text-sm leading-snug">
                  {#each s.readings as r}
                    <li>
                      {#if r.url}
                        <a href={r.url} target="_blank" rel="noopener noreferrer" class="underline underline-offset-2 hover:text-gray-700">{r.title}</a>
                      {:else}
                        {r.title}
                      {/if}
                    </li>
                  {/each}
                </ul>
              </div>
            {/if}

            {#if s.background?.length}
              <div class="mt-3">
                <h4 class="text-sm font-medium text-neutral-600">Background</h4>
                <ul class="mt-1 space-y-1 text-sm leading-snug">
                  {#each s.background as r}
                    <li>
                      {#if r.url}
                        <a href={r.url} target="_blank" rel="noopener noreferrer" class="underline underline-offset-2 hover:text-gray-700">{r.title}</a>
                      {:else}
                        {r.title}
                      {/if}
                    </li>
                  {/each}
                </ul>
              </div>
            {/if}

            {#if s.media?.length}
              <div class="mt-3">
                <h4 class="text-sm font-medium text-neutral-600">Optional Art/Media</h4>
                <ul class="mt-1 space-y-1 text-sm leading-snug">
                  {#each s.media as r}
                    <li>
                      {#if r.url}
                        <a href={r.url} target="_blank" rel="noopener noreferrer" class="underline underline-offset-2 hover:text-gray-700">{r.title}</a>
                      {:else}
                        {r.title}
                      {/if}
                    </li>
                  {/each}
                </ul>
              </div>
            {/if}
          </article>
        {/each}
      </div>

      <!-- Desktop: minimal table -->
      <div class="hidden md:block overflow-x-auto rounded-xl border border-neutral-200">
        <table class="w-full text-left text-sm">
          <thead class="bg-neutral-50 text-neutral-600">
            <tr>
              <th class="px-4 py-3 w-32">Date</th>
              <th class="px-4 py-3 w-80">Theme</th>
              <th class="px-4 py-3">Readings</th>
              <th class="px-4 py-3">Background</th>
              <th class="px-4 py-3">Optional Art/Media</th>
            </tr>
          </thead>
          <tbody>
            {#each sessions_2425 as s, i}
              <tr class={i % 2 ? 'bg-white' : 'bg-neutral-50/40'}>
                <td class="align-top px-4 py-3 whitespace-nowrap text-neutral-700">{s.date}</td>
                <td class="align-top px-4 py-3 font-semibold">{s.theme}</td>
                <td class="align-top px-4 py-3">
                  {#if s.readings?.length}
                    <ul class="list-disc pl-5 space-y-1">
                      {#each s.readings as r}
                        <li>
                          {#if r.url}
                            <a href={r.url} target="_blank" rel="noopener noreferrer" class="underline underline-offset-2 hover:text-gray-700">{r.title}</a>
                          {:else}
                            {r.title}
                          {/if}
                        </li>
                      {/each}
                    </ul>
                  {/if}
                </td>
                <td class="align-top px-4 py-3">
                  {#if s.background?.length}
                    <ul class="list-disc pl-5 space-y-1">
                      {#each s.background as r}
                        <li>
                          {#if r.url}
                            <a href={r.url} target="_blank" rel="noopener noreferrer" class="underline underline-offset-2 hover:text-gray-700">{r.title}</a>
                          {:else}
                            {r.title}
                          {/if}
                        </li>
                      {/each}
                    </ul>
                  {/if}
                </td>
                <td class="align-top px-4 py-3">
                  {#if s.media?.length}
                    <ul class="list-disc pl-5 space-y-1">
                      {#each s.media as r}
                        <li>
                          {#if r.url}
                            <a href={r.url} target="_blank" rel="noopener noreferrer" class="underline underline-offset-2 hover:text-gray-700">{r.title}</a>
                          {:else}
                            {r.title}
                          {/if}
                        </li>
                      {/each}
                    </ul>
                  {/if}
                </td>
              </tr>
            {/each}
          </tbody>
        </table>
      </div>
    {/if}
  </div>
</section>

<Footer/>

<style>
  /* In case Tailwind isn’t available, keep it readable */
  :global(html) { font-family: 'Space Grotesk', system-ui, -apple-system, Segoe UI, Roboto, sans-serif; }
</style>
