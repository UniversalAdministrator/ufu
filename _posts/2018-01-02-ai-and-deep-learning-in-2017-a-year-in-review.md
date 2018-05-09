---
ID: 3953
post_title: >
  AI and Deep Learning in 2017 – A Year
  in Review
author: UfU
post_excerpt: ""
layout: post
permalink: >
  http://universalflowuniversity.com/ai/ai-and-deep-learning-in-2017-a-year-in-review/
published: true
post_date: 2018-01-02 19:50:03
---
<header class="entry-header"></header>
<div class="entry-content">
<div class="entry-meta"><span class="byline">BY <span class="author vcard"><a class="url fn n" href="http://www.wildml.com/author/dennybritz/">DENNY BRITZ</a></span></span></div>
The year is coming to an end. I did not write nearly as much as I had planned to. But I’m hoping to change that next year, with more tutorials around Reinforcement Learning, Evolution, and Bayesian Methods coming to WildML! And what better way to start than with a summary of all the amazing things that happened in 2017? Looking back through my Twitter history and the <a href="https://www.getrevue.co/profile/wildml">WildML newsletter</a>, the following topics repeatedly came up. I’ll inevitably miss some important milestones, so please let me know about it in the comments!
<h3>Reinforcement Learning beats humans at their own games</h3>
The biggest success story of the year was probably <a href="https://deepmind.com/research/alphago/">AlphaGo</a> (<a href="https://storage.googleapis.com/deepmind-media/alphago/AlphaGoNaturePaper.pdf">Nature paper</a>), a Reinforcement Learning agent that beat the world’s best Go players. Due to its extremely large search space, Go was thought to be out of reach of Machine Learning techniques for a couple more years. What a nice surprise!

The first version of AlphaGo was bootstrapped using training data from human experts and further improved through self-play and an adaptation of Monte-Carlo Tree Search. Soon after, <a href="https://deepmind.com/blog/alphago-zero-learning-scratch/">AlphaGo Zero</a> (<a href="https://www.nature.com/articles/nature24270.epdf?author_access_token=VJXbVjaSHxFoctQQ4p2k4tRgN0jAjWel9jnR3ZoTv0PVW4gB86EEpGqTRDtpIz-2rmo8-KG06gqVobU5NSCFeHILHcVFUeMsbvwS-lxjqQGg98faovwjxeTUgZAUMnRQ">Nature Paper</a>) took it a step further and learned to play Go from scratch, without human training data whatsoever, using a technique a technique previously published in the <a href="https://arxiv.org/abs/1705.08439">Thinking Fast and Slow with Deep Learning and Tree Search</a> paper. It also handily beat the first version of AlphaGo. Towards the end of the year, we saw yet another generalization of the AlphaGo Zero algorithm, called <a href="https://arxiv.org/abs/1712.01815">AlphaZero</a>, which not only mastered Go, but also Chess and Shogi, using the exact same techniques. Interestingly, these programs made moves that surprised even the most experienced Go players, motivating players to learn from AlphaGo and adjusting their own play style accordingly. To make this easier, DeepMind also released an <a href="https://alphagoteach.deepmind.com/">AlphaGo Teach</a> tool.

<img class="alignnone wp-image-3954 size-full" src="https://universalflowuniversity.com/wp-content/uploads/2018/01/Screen-Shot-2017-12-31-at-10.20.54-PM.png" alt="" width="2146" height="786" />

<a href="http://d3kbpzbmcynnmx.cloudfront.net/wp-content/uploads/2017/12/Screen-Shot-2017-12-31-at-10.20.54-PM.png"><img class="aligncenter size-full wp-image-1083" src="http://d3kbpzbmcynnmx.cloudfront.net/wp-content/uploads/2017/12/Screen-Shot-2017-12-31-at-10.20.54-PM.png" sizes="(max-width: 767px) 89vw, (max-width: 1000px) 54vw, (max-width: 1071px) 543px, 580px" srcset="http://d3kbpzbmcynnmx.cloudfront.net/wp-content/uploads/2017/12/Screen-Shot-2017-12-31-at-10.20.54-PM.png 2146w, http://d3kbpzbmcynnmx.cloudfront.net/wp-content/uploads/2017/12/Screen-Shot-2017-12-31-at-10.20.54-PM-300x110.png 300w, http://d3kbpzbmcynnmx.cloudfront.net/wp-content/uploads/2017/12/Screen-Shot-2017-12-31-at-10.20.54-PM-768x281.png 768w, http://d3kbpzbmcynnmx.cloudfront.net/wp-content/uploads/2017/12/Screen-Shot-2017-12-31-at-10.20.54-PM-1024x375.png 1024w" alt="" width="2146" height="786" /></a>

But Go wasn’t the only game where we made significant progress. <a href="https://www.wired.com/2017/02/libratus/">Libratus</a> (<a href="http://science.sciencemag.org/content/early/2017/12/15/science.aao1733.full">Science paper</a>), a system developed by researchers from CMU, managed to beat top Poker players in a 20-day Heads-up, No-Limit Texas Hold’em tournament. A little earlier, <a href="https://www.deepstack.ai/">DeepStack</a>, a system developed by researchers from Charles University, The Czech Technical University, and the University of Alberta, became the first to beat professional poker players. Note that both of these systems played Heads-up poker, which is played between two players and a significantly easier problem than playing at a table of multiple players. The latter will most likely see additional progress in 2018.

The next frontiers for Reinforcement Learning seem to be more complex multi-player games, including multi-player Poker. DeepMind is actively working on Starcraft 2, releasing a <a href="https://deepmind.com/blog/deepmind-and-blizzard-open-starcraft-ii-ai-research-environment/">research environment</a>, and OpenAI demonstrated <a href="https://blog.openai.com/dota-2/">initial success in 1v1 Dota 2</a>, with the goal of competing in the the full 5v5 game in the near future.
<h3>Evolution Algorithms make a Comeback</h3>
For supervised learning, gradient-based approaches using the back-propagation algorithm have been working extremely well. And that isn’t likely to change anytime soon. However, in Reinforcement Learning, Evolution Strategies (ES) seem to be making a comeback. Because the data typically is not iid (independent and identically distributed), error signals are sparser, and because there is a need for exploration, algorithms that do not rely on gradients can work quite well. In addition, evolutionary algorithms can scale linearly to thousands of machines enabling extremely fast parallel training. They do not require expensive GPUs, but can be trained on a large number (typically hundreds to thousands) of cheap CPUs.

Earlier in the year, researchers from OpenAI <a href="https://blog.openai.com/evolution-strategies/">demonstrated</a> that Evolution Strategies can achieve performance comparable to standard Reinforcement Learning algorithms such as Deep Q-Learning. Towards the end of the year, a team from Uber released <a href="https://eng.uber.com/deep-neuroevolution/">a blog post and a set of five research papers</a>, further demonstrating the potential of Genetic Algorithms and novelty search. Using an extremely simple Genetic Algorithm, and no gradient information whatsoever, their algorithm learns to play difficult Atari Games. Here’s a video of the GA policy scoreing 10,500 on Frostbite. DQN, AC3, and ES score less than 1,000 on this game.

</div>
&nbsp;

&nbsp;

[embed]https://eng.uber.com/wp-content/uploads/2017/12/frostbite_ga_noframeskip.mp4[/embed]
<div class="entry-content">
<div class="wp-video">
<div id="mep_0" class="mejs-container mejs-container-keyboard-inactive wp-video-shortcode mejs-video" tabindex="0" role="application" aria-label="Video Player">
<div class="mejs-inner">
<div class="mejs-controls">
<div class="mejs-button mejs-fullscreen-button"></div>
</div>
</div>
</div>
</div>
&nbsp;

&nbsp;

&nbsp;

&nbsp;

&nbsp;

&nbsp;

&nbsp;

&nbsp;

Most likely, we’ll see more work in this direction in 2018.
<h3>WaveNets, CNNs, and Attention Mechanisms</h3>
Google’s <a href="https://research.googleblog.com/2017/12/tacotron-2-generating-human-like-speech.html">Tacotron 2 text-to-speech system</a> produces extremely impressive <a href="https://google.github.io/tacotron/publications/tacotron2/index.html">audio samples</a> and is based on <a href="https://deepmind.com/blog/wavenet-generative-model-raw-audio/">WaveNet</a>, an autoregressive model which is also deployed in the Google Assistant and has seen <a href="https://deepmind.com/blog/high-fidelity-speech-synthesis-wavenet/">massive speed improvements</a> in the past year. WaveNet had previously been applied to Machine Translation as well, resulting in faster training times that recurrent architectures.

The move away from expensive recurrent architectures that take long to train seems to be larger trend in Machine Learning subfields. In <a href="https://arxiv.org/abs/1706.03762">Attention is All you Need</a>, researchers get rid of recurrence and convolutions entirely, and use a more sophisticated attention mechanism to achieve state of the art results at a fraction of the training costs.
<h3>The Year of Deep Learning frameworks</h3>
If I had to summarize 2017 in one sentence, it would be the year of frameworks. Facebook made a big splash with <a href="http://pytorch.org/">PyTorch</a>. Due to its dynamic graph construction similar to what <a href="https://chainer.org/">Chainer</a> offers, PyTorch received much love from researchers in Natural Language Processing, who regularly have to deal with dynamic and recurrent structures that hard to declare in a static graph frameworks such as Tensorflow.

Tensorflow had quite a run in 2017. <a href="https://github.com/tensorflow/tensorflow/releases/tag/v1.0.0">Tensorflow 1.0</a> with a stable and backwards-compatible API was released in February. Currently, Tensorflow is at version 1.4.1. In addition to the main framework, several Tensorflow companion libraries were released, including <a href="https://research.googleblog.com/2017/02/announcing-tensorflow-fold-deep.html">Tensorflow Fold</a> for dynamic computation graphs, <a href="https://research.googleblog.com/2017/02/preprocessing-for-machine-learning-with.html">Tensorflow Transform</a> for data input pipelines, and <a href="https://deepmind.com/blog/open-sourcing-sonnet/">DeepMind’s higher-level Sonnet library</a>. The Tensorflow team also announced a new <a href="https://research.googleblog.com/2017/10/eager-execution-imperative-define-by.html">eager execution</a> mode which works similar to PyTorch’s dynamic computation graphs.

In addition to Google and Facebook, many other companies jumped on the Machine Learning framework bandwagon:
<ul>
 	<li>Apple announced its <a href="https://developer.apple.com/machine-learning/">CoreML</a> mobile machine learning library.</li>
 	<li>A team at Uber released <a href="https://eng.uber.com/pyro/">Pyro</a>, a Deep Probabilistic Programming Language.</li>
 	<li>Amazon announced <a href="https://github.com/gluon-api/gluon-api/">Gluon</a>, a higher-level API available in MXNet.</li>
 	<li>Uber released details about its internal <a href="https://eng.uber.com/michelangelo/">Michelangelo</a> Machine Learning infrastructure platform.</li>
</ul>
And because the number of framework is getting out of hand, Facebook and Microsoft announced the <a href="https://onnx.ai/">ONNX</a> open format to share deep learning models across frameworks. For example, you may train your model in one framework, but then serve it in production in another one.

In addition to general-purpose Deep Learning frameworks, we saw a large number of Reinforcement Learning frameworks being released, including:
<ul>
 	<li><a href="https://blog.openai.com/roboschool/">OpenAI Roboschool</a> is an open-source software for robot simulation.</li>
 	<li><a href="https://github.com/openai/baselines">OpenAI Baselines</a> is a set of high-quality implementations of reinforcement learning algorithms.</li>
 	<li><a href="https://github.com/tensorflow/agents">Tensorflow Agents</a> contains optimized infrastructure for training RL agents using Tensorflow.</li>
 	<li><a href="https://github.com/Unity-Technologies/ml-agents">Unity ML Agents</a> allows researchers and developers to create games and simulations using the Unity Editor and train them using Reinforcement Learning.</li>
 	<li><a href="http://coach.nervanasys.com/">Nervana Coach</a> allows experimentation with state of the art Reinforcement Learning algorithms.</li>
 	<li><a href="https://code.facebook.com/posts/132985767285406/introducing-elf-an-extensive-lightweight-and-flexible-platform-for-game-research/">Facebook’s ELF</a> platform for game research.</li>
 	<li><a href="https://github.com/deepmind/pycolab">DeepMind Pycolab</a> is a customizable gridworld game engine.</li>
 	<li><a href="https://github.com/geek-ai/MAgent">Geek.ai MAgent</a> is a research platform for many-agent reinforcement learning.</li>
</ul>
With the goal of making Deep Learning more accessible, we also got a few frameworks for the web, such as <a href="https://deeplearnjs.org/">Google’s deeplearn.js</a>and the <a href="https://mil-tokyo.github.io/webdnn/">MIL WebDNN</a> execution framework. But at least one very popular framework died. That was <a href="http://deeplearning.net/software/theano/">Theano</a>. In an <a href="https://groups.google.com/forum/#!topic/theano-users/7Poq8BZutbY">announcement</a>on the Theano mailing list, the developers decided that 1.0 would be its last release.
<h3>Learning Resources</h3>
With Deep Learning and Reinforcement Learning gaining popularity, an increasing number of lectures, bootcamps, and events have been recorded and published online in 2017. The following are some of my favorites:
<ul>
 	<li>The <a href="https://sites.google.com/view/deep-rl-bootcamp/lectures?authuser=0">Deep RL Bootcamp</a> co-hosted by OpenAI and UC Berkeley featured lectures about Reinforcement Learning basics as well as state-of-the-art research.</li>
 	<li>The Spring 2017 version of Stanford’s <a href="https://www.youtube.com/playlist?list=PL3FW7Lu3i5JvHM8ljYj-zLfQRF3EO8sYv">Convolutional Neural Networks for Visual Recognition</a> course. Also check out the <a href="http://cs231n.stanford.edu/">course website</a>.</li>
 	<li>The Winter 2017 version of Stanford’s <a href="https://www.youtube.com/playlist?list=PL3FW7Lu3i5Jsnh1rnUwq_TcylNr7EkRe6">Natural Language Processing with Deep Learning</a> course. Also check out the <a href="http://web.stanford.edu/class/cs224n/">course website</a>.</li>
 	<li>Stanford’s <a href="https://stats385.github.io/">Theories of Deep Learning</a> course.</li>
 	<li>The new <a href="https://www.coursera.org/specializations/deep-learning">Coursera Deep Learning specialization</a></li>
 	<li>The <a href="http://videolectures.net/deeplearning2017_montreal/">Deep Learning and Reinforcement Summer School in Montreal</a></li>
 	<li>UC Berkeley’s <a href="http://rll.berkeley.edu/deeprlcourse/">Deep Reinforcement Learning Fall 2017 course</a>.</li>
 	<li>The <a href="https://www.youtube.com/playlist?list=PLOU2XLYxmsIKGc_NBoIhTn2Qhraji53cv">Tensorflow Dev Summit</a> with talks on Deep Learning basics and relevant Tensorflow APIs.</li>
</ul>
Several academic conferences continued the new tradition of publishing conference talks online. If you want to catch up with cutting-edge research you can watch some of the recordings from <a href="https://nips.cc/Conferences/2017/Videos">NIPS 2017</a>, <a href="https://www.facebook.com/pg/iclr.cc/videos/">ICLR 2017</a> or <a href="https://ku.cloud.panopto.eu/Panopto/Pages/Sessions/List.aspx">EMNLP 2017</a>.

Researchers also started publishing easily accessible tutorial and survey papers on arXiv. Here are some of my favorites from this year:
<ul>
 	<li><a href="https://arxiv.org/abs/1701.07274">Deep Reinforcement Learning: An Overview</a></li>
 	<li><a href="https://arxiv.org/abs/1709.02840">A Brief Introduction to Machine Learning for Engineers</a></li>
 	<li><a href="https://arxiv.org/abs/1709.07809">Neural Machine Translation</a></li>
 	<li><a href="https://arxiv.org/abs/1703.01619">Neural Machine Translation and Sequence-to-sequence Models: A Tutorial</a></li>
</ul>
<h3>Applications: AI &amp; Medicine</h3>
2017 saw many bold claims about Deep Learning techniques solving medical problems and beating human experts. There was a lot of hype, and understanding true breakthroughs is anything but easy for someone not coming from a medical background. For an comprehensive review, I recommend Luke Oakden-Rayner’s <a href="https://lukeoakdenrayner.wordpress.com/2017/04/20/the-end-of-human-doctors-introduction/">The End of Human Doctors blog post series</a>. I will briefly highlight some developments here.

Among the top news this year was a Stanford team releasing details about <a href="https://cs.stanford.edu/people/esteva/nature/">a Deep learning algorithm that does as well as dermatologists in identifying skin cancer</a>. You can read the <a href="https://www.nature.com/articles/nature21056.epdf?author_access_token=8oxIcYWf5UNrNpHsUHd2StRgN0jAjWel9jnR3ZoTv0NXpMHRAJy8Qn10ys2O4tuPakXos4UhQAFZ750CsBNMMsISFHIKinKDMKjShCpHIlYPYUHhNzkn6pSnOCt0Ftf6">Nature article here</a>. Another team at Stanford <a href="https://stanfordmlgroup.github.io/projects/ecg/">developed a model which can diagnose irregular heart rhythms, also known as arrhythmias, from single-lead ECG signals better than a cardiologist</a>.

<img class="alignnone size-full wp-image-3955" src="https://universalflowuniversity.com/wp-content/uploads/2018/01/Screen-Shot-2017-12-31-at-10.50.06-PM-768x724.png" alt="" width="768" height="724" />

<a href="http://d3kbpzbmcynnmx.cloudfront.net/wp-content/uploads/2017/12/Screen-Shot-2017-12-31-at-10.50.06-PM.png"><img class="aligncenter size-large wp-image-1084" src="http://d3kbpzbmcynnmx.cloudfront.net/wp-content/uploads/2017/12/Screen-Shot-2017-12-31-at-10.50.06-PM-1024x966.png" sizes="(max-width: 525px) 100vw, 525px" srcset="http://d3kbpzbmcynnmx.cloudfront.net/wp-content/uploads/2017/12/Screen-Shot-2017-12-31-at-10.50.06-PM-1024x966.png 1024w, http://d3kbpzbmcynnmx.cloudfront.net/wp-content/uploads/2017/12/Screen-Shot-2017-12-31-at-10.50.06-PM-300x283.png 300w, http://d3kbpzbmcynnmx.cloudfront.net/wp-content/uploads/2017/12/Screen-Shot-2017-12-31-at-10.50.06-PM-768x724.png 768w" alt="" width="525" height="495" /></a>

But this year was not without blunders. DeepMind’s deal with the NHS <a href="http://www.businessinsider.com/deepmind-royal-free-london-nhs-deal-inexcusable-mistakes-2017-3">was full of “inexcusable” mistakes</a>. The NIH released a <a href="https://www.nih.gov/news-events/news-releases/nih-clinical-center-provides-one-largest-publicly-available-chest-x-ray-datasets-scientific-community">chest x-ray dataset</a> to the scientific community, but <a href="https://lukeoakdenrayner.wordpress.com/2017/12/18/the-chestxray14-dataset-problems/">upon closer inspection</a> it was found that it is not really suitable for training diagnostic AI models.
<h3>Applications: Art &amp; GANs</h3>
Another application that started to gain more traction this year is generative modeling for images, music, sketches, and videos. The NIPS 2017 conference featured a <a href="https://nips2017creativity.github.io/">Machine Learning for Creativity and Design</a> workshop the first time this year.

Among the most popular applications was <a href="https://quickdraw.withgoogle.com/">Google’s QuickDraw</a>, which uses a neural network to recognize your doodles. Using the released dataset you may even teach machines to <a href="https://research.googleblog.com/2017/04/teaching-machines-to-draw.html">finish your drawings for you</a>.

Generative Adversarial Networks (GANs), made significant progress this year. New models such as <a href="https://arxiv.org/abs/1703.10593">CycleGAN</a>, <a href="https://github.com/carpedm20/DiscoGAN-pytorch">DiscoGAN</a> and <a href="https://github.com/yunjey/StarGAN">StarGAN</a> achieved impressive results in generating faces, for example. GANs traditionally have had difficulty generating realistic high-resolution images, but impressive results from <a href="https://tcwang0509.github.io/pix2pixHD/">pix2pixHD</a> demonstrate that we’re on track to solving these. Will GANs become the new paintbrush?
<h3>Applications: Self-driving cars</h3>
The big players in the self-driving car space are ride-sharing apps Uber and Lyft, Alphabet’s Waymo, and Tesla. Uber started out the year with a few setbacks as their self-driving cars <a href="http://fortune.com/2017/02/26/uber-self-driving-car-red-lights/">missed several red lights</a> in San Francisco due to software error, not human error as had been reported previously. Later on, Uber shared <a href="https://eng.uber.com/atg-dataviz/">details about its car visualization platform</a> used internally. In December, Uber’s self driving car program <a href="https://www.forbes.com/sites/bizcarson/2017/12/22/ubers-self-driving-cars-2-million-miles/#23dc88eaa4fe">hit 2 million miles</a>.

In the meantime, Waymo’s self-driving cars <a href="https://www.bloomberg.com/news/articles/2017-04-25/alphabet-s-self-driving-cars-to-get-their-first-real-riders">got their first real riders in April</a>, and later <a href="https://www.recode.net/2017/11/7/16614780/alphabet-driverless-cars-phoenix-arizona">completely took out the human operators in Phoenix, Arizona</a>. Waymo also published details about their <a href="https://www.theatlantic.com/technology/archive/2017/08/inside-waymos-secret-testing-and-simulation-facilities/537648/">testing and simulation technology</a>.
<figure class="wp-caption aligncenter"><img class="size-large" src="https://cdn.theatlantic.com/assets/media/img/posts/2017/08/WaymoMovieGIF/a7325709f.gif" width="640" height="398" /></figure>
A Waymo simulation showing improved vehicle navigationLyft announced that it is <a href="https://www.recode.net/2017/7/21/16005164/lyft-self-driving-cars-autonomous-software-hardware">building its own autonomous driving hard- and software</a>. Its first pilot in Boston is <a href="https://www.theverge.com/2017/12/6/16742924/lyft-nutonomy-boston-self-driving-car">now underway</a>. Tesla Autpilot hasn’t <a href="https://www.theverge.com/2017/10/24/16504038/tesla-autopilot-self-driving-update-elon-musk">seen much of an update</a>, but there’s a newcomer to the space: Apple. Tim Cook <a href="https://www.theverge.com/2017/6/13/15790076/apple-self-driving-cars-autonomous-tim-cook">confirmed</a> that Apple is working on software for self-driving cars, and researchers from Apple <a href="https://arxiv.org/abs/1711.06396">published</a> a mapping-related paper on arXiv.
<h3>Applications: Cool Research Projects</h3>
So many interesting projects and demos were published this year that it’s impossible to mention all of them here. However, here are a couple the stood out during the year:
<ul>
 	<li><a href="https://towardsdatascience.com/background-removal-with-deep-learning-c4f2104b3157">Background removal with Deep Learning</a></li>
 	<li><a href="http://make.girls.moe/#/">Creating Anime characters with Deep Learning</a></li>
 	<li><a href="https://blog.floydhub.com/colorizing-b&amp;w-photos-with-neural-networks/">Colorizing B&amp;W Photos with Neural Networks</a></li>
 	<li><a href="https://www.polygon.com/2017/11/5/16610012/mario-kart-mariflow-neural-network-video">Mario Kart (SNES) played by a neural network</a></li>
 	<li><a href="https://github.com/rameshvarun/NeuralKart">A Real-time Mario Kart 64 AI</a></li>
 	<li><a href="https://www.technologyreview.com/s/609524/this-ai-can-spot-art-forgeries-by-looking-at-one-brushstroke/">Spotting Forgeries using Deep Learning</a></li>
 	<li><a href="https://affinelayer.com/pixsrv/index.html">Edges to Cats</a></li>
</ul>
And on the more research-y side:
<ul>
 	<li><a href="https://blog.openai.com/unsupervised-sentiment-neuron/">The Unsupervised Sentiment Neuron</a> – A system which learns an excellent representation of sentiment, despite being trained only to predict the next character in the text of Amazon reviews.</li>
 	<li><a href="https://blog.openai.com/learning-to-communicate/">Learning to Communicate</a> – Research in which agents develop their own language.</li>
 	<li><a href="https://arxiv.org/abs/1712.01208">The Case for Learning Index Structures</a> – Using neural nets to outperform cache-optimized B-Trees by up to 70% in speed while saving an order-of-magnitude in memory over several real-world data set.</li>
 	<li><a href="https://arxiv.org/abs/1706.03762">Attention is All You Need</a></li>
 	<li><a href="https://arxiv.org/abs/1703.06870">Mask R-CNN</a> – A general framework for object instance segmentation</li>
 	<li><a href="https://dmitryulyanov.github.io/deep_image_prior">Deep Image Prior for denoising, superresolution, and inpainting</a></li>
</ul>
<h3>Datasets</h3>
Neural Networks used for supervised learning are notoriously data hungry. That’s why open datasets are an incredibly important contribution to the research community. The following are a few datasets that stood out this year:
<ul>
 	<li><a href="https://research.google.com/youtube-bb">Youtube Bounding Boxes</a></li>
 	<li><a href="https://quickdraw.withgoogle.com/data">Google QuickDraw Data</a></li>
 	<li><a href="https://deepmind.com/research/open-source/open-source-datasets">DeepMind Open Source Datasets</a></li>
 	<li><a href="https://research.googleblog.com/2017/08/launching-speech-commands-dataset.html">Google Speech Commands Dataset</a></li>
 	<li><a href="https://research.google.com/ava/">Atomic Visual Actions</a></li>
 	<li><a href="https://github.com/openimages/dataset">Several updates to the Open Images data set</a></li>
 	<li><a href="https://magenta.tensorflow.org/datasets/nsynth">Nsynth dataset of annotated musical notes</a></li>
 	<li><a href="https://data.quora.com/First-Quora-Dataset-Release-Question-Pairs">Quora Question Pairs</a></li>
</ul>
<h3>Deep Learning, Reproducibility, and Alchemy</h3>
Throughout the year, several researchers raised concerns about the reproducibility of academic paper results. Deep Learning models often rely on a huge number of hyperparameters which must to be optimized in order to achieve results that are good enough to publish. This optimization can become so expensive that only companies such as Google and Facebook can afford it. Researchers do not always release their code, forget to put important details into the finished paper, use slightly different evaluation procedures, or overfit to the dataset by repeatedly optimizing hyperparameters on the same splits. This makes reproducibility a big issue. In <a href="https://arxiv.org/abs/1709.06560">Reinforcement Learning That Matters</a>, researchers showed that the same algorithms taken from different code bases achieve vastly different results with high variance:

<a href="http://d3kbpzbmcynnmx.cloudfront.net/wp-content/uploads/2017/12/Screen-Shot-2017-12-31-at-11.09.51-PM.png"><img class="aligncenter size-large wp-image-1086" src="http://d3kbpzbmcynnmx.cloudfront.net/wp-content/uploads/2017/12/Screen-Shot-2017-12-31-at-11.09.51-PM-1024x973.png" sizes="(max-width: 525px) 100vw, 525px" srcset="http://d3kbpzbmcynnmx.cloudfront.net/wp-content/uploads/2017/12/Screen-Shot-2017-12-31-at-11.09.51-PM-1024x973.png 1024w, http://d3kbpzbmcynnmx.cloudfront.net/wp-content/uploads/2017/12/Screen-Shot-2017-12-31-at-11.09.51-PM-300x285.png 300w, http://d3kbpzbmcynnmx.cloudfront.net/wp-content/uploads/2017/12/Screen-Shot-2017-12-31-at-11.09.51-PM-768x729.png 768w, http://d3kbpzbmcynnmx.cloudfront.net/wp-content/uploads/2017/12/Screen-Shot-2017-12-31-at-11.09.51-PM.png 1472w" alt="" width="525" height="499" /></a>

In <a href="https://arxiv.org/abs/1711.10337">Are GANs Created Equal? A Large-Scale Study</a>, researchers showed that a well-tuned GAN using expensive hyperparameter search can beat more sophisticated approaches that claim to be superior. Similarly, in <a href="https://arxiv.org/abs/1707.05589">On the State of the Art of Evaluation in Neural Language Models</a>, researchers showed that simple LSTM architectures, when properly regularized and tuned, can outperform more recent models.

In a NIPS talk that resonated with many researchers, Ali Rahimi <a href="https://www.youtube.com/watch?v=Qi1Yry33TQE">compared recent Deep Learning approaches to Alchemy</a> and called for more rigorous experimental design. Yann LeCun took it as an insult and promptly <a href="https://www.facebook.com/yann.lecun/posts/10154938130592143">responded</a> the next day.
<h3>Artificial Intelligence made in Canada and China</h3>
With United States immigration policies tightening, it seems that companies are increasingly opening offices overseas, with Canada being a prime destination. Google opened a <a href="https://canada.googleblog.com/2017/03/canadas-ai-moment.html">new office in Toronto</a>, DeepMind opened a new office in <a href="https://deepmind.com/blog/deepmind-office-canada-edmonton/">Edmonton, Canada</a>, and Facebook AI Research is <a href="https://newsroom.fb.com/news/2017/09/fair-montreal/">expanding to Montreal</a> as well.

China is another destination that is receiving a lot of attention. With a lot of capital, a large talent pool, and government data readily available, it is <a href="https://www.nytimes.com/2017/07/20/business/china-artificial-intelligence.html">competing</a> head to head with the United States in terms of AI developments and production deployments. Google also announced that it will soon open a <a href="https://www.bloomberg.com/news/articles/2017-12-13/google-to-open-beijing-ai-center-in-latest-expansion-in-china">new lab in Beijing</a>.
<h3>Hardware Wars: Nvidia, Intel, Google, Tesla</h3>
Modern Deep Learning techniques famously require expensive GPUs to train state-of-the-art models. So far, NVIDIA has been the big winner. This year, it announced its new <a href="https://www.nvidia.com/en-us/titan/titan-v/">Titan V</a> flagship GPU. It comes in gold color, by the way.

But competition is increasing. Google’s TPUs <a href="https://blog.google/topics/google-cloud/google-cloud-offer-tpus-machine-learning/">are now available on its cloud platform</a>, Intel’s Nervana <a href="https://www.theverge.com/circuitbreaker/2017/10/17/16488414/intel-ai-chips-nervana-neural-network-processor-nnp">unveiled a new set of chips</a>, and even Tesla admitted that it is <a href="https://www.theregister.co.uk/2017/12/08/elon_musk_finally_admits_tesla_is_building_its_own_custom_ai_chips/">working on its own AI hardware</a>. Competition may also <a href="https://qz.com/1053799/chinas-bitmain-dominates-bitcoin-mining-now-it-wants-to-cash-in-on-artificial-intelligence/">come from China</a>, where hardware makers specializing in Bitcoin mining want to enter the Artificial Intelligence focused GPU space.
<h3>Hype and Failures</h3>
With great hype comes great responsibility. What the mainstream media reports almost never corresponds to what actually happened in a research lab or production system. IBM Watson is the poster-child over overhyped marketing and failed to deliver corresponding results. This year, <a href="https://gizmodo.com/why-everyone-is-hating-on-watson-including-the-people-w-1797510888">everyone was hating on IBM Watson</a>, which is not surprising after its <a href="https://www.statnews.com/2017/09/05/watson-ibm-cancer/">repeated failures in healthcare</a>.

The story capturing the most hype was probably Facebook’s “Researchers shut down AI that invented its own language”, which I won’t link to on purpose. It has already done enough damage and you can google it. Of course, the title couldn’t have been further from the truth. What happened was researchers stopping a standard experiment that did not seem to give good results.

But it’s not only the press that is guilty of hype. Researchers also overstepped boundaries with titles and abstracts that do not reflect the actual experiment results, such as in this <a href="https://medium.com/@yoav.goldberg/an-adversarial-review-of-adversarial-generation-of-natural-language-409ac3378bd7">natural language generation paper</a>, or this <a href="http://zacharydavid.com/2017/08/06/fitting-to-noise-or-nothing-at-all-machine-learning-in-markets/">Machine Learning for markets</a>paper.
<h3>High-Profile Hires and Departures</h3>
Andrew Ng, the Coursera co-founder who is probably most famous for his Machine Learning MOOC, was in the news several times this year. Andrew <a href="https://medium.com/@andrewng/opening-a-new-chapter-of-my-work-in-ai-c6a4d1595d7b">left Baidu</a> where he was leading the AI group in March, <a href="https://techcrunch.com/2017/08/15/andrew-ng-is-raising-a-150m-ai-fund">raised</a> a new $150M fund, and announced a new startup, <a href="https://www.landing.ai/">landing.ai</a>, focused on the manufacturing industry. In other news, <a href="https://www.recode.net/2017/3/8/14863560/uber-ai-gary-marcus-geometric-intelligence">Gary Marcus stepped down as the director of Uber’s artificial intelligence lab</a>, Facebook <a href="https://venturebeat.com/2017/06/14/facebook-hires-siri-natural-language-understanding-chief-from-apple/">hired away Siri’s Natural Language Understanding Chief</a>, and several prominent several researchers <a href="https://www.theverge.com/2017/11/10/16627570/robot-ai-grasping-grabbing-embodied-intelligence-startup">left OpenAI to start a new robotics company</a>.

The trend of Academia losing scientists to the industry also <a href="https://www.theguardian.com/science/2017/nov/01/cant-compete-universities-losing-best-ai-scientists">continued</a>, with university labs complaining that they cannot compete with the salaries offered by the industry giants.
<h3>Startup Investments and Acquisitions</h3>
Just like the year before, the AI startup ecosystem was booming with several high-profile acquisitions:
<ul>
 	<li><a href="https://blogs.microsoft.com/blog/2017/01/13/microsoft-acquires-deep-learning-startup-maluuba-ai-pioneer-yoshua-bengio-advisory-role/">Microsoft acquired deep learning startup Maluuba</a></li>
 	<li><a href="https://cloudplatform.googleblog.com/2017/03/welcome-Kaggle-to-Google-Cloud.html">Google Cloud acquired Kaggle</a></li>
 	<li><a href="https://www.bloomberg.com/news/articles/2017-06-09/softbank-agrees-to-buy-robot-maker-boston-dynamics">Softbank bought robot maker Boston Dynamics</a> (which famously does not use much Machine Learning)</li>
 	<li><a href="https://venturebeat.com/2017/07/31/facebook-acquires-ai-assistant-startup-ozlo/">Facebook bought AI assistant startup Ozlo</a></li>
 	<li><a href="https://techcrunch.com/2017/11/28/samsung-buys-another-ai-company-as-it-continues-to-build-out-bixby/">Samsung acquired Fluently to build out Bixby</a></li>
</ul>
… and new companies raising large sums of money:
<ul>
 	<li><a href="https://venturebeat.com/2017/03/22/mythic-raises-8-8-million-to-put-ai-on-a-chip">Mythic raised $8.8 million to put AI on a chip</a></li>
 	<li><a href="https://techcrunch.com/2017/06/14/element-ai-a-platform-for-companies-to-build-ai-solutions-raises-102m/">Element AI, a platform for companies to build AI solutions, raised $102M</a></li>
 	<li><a href="https://www.forbes.com/sites/alanohnsman/2017/06/27/robot-car-tech-startup-drive-ai-raises-50-million-adds-stanfords-ng-to-board/">Drive.ai raised $50M and added Andrew Ng to its board</a></li>
 	<li><a href="https://www.graphcore.ai/posts/big-names-in-machine-intelligence-join-graphcores-new-30-million-funding-round">Graphcore raised $30M</a></li>
 	<li><a href="https://techcrunch.com/2017/08/29/ai-startup-appier-gets-33m-series-c-from-investors-including-softbank-group-line-corp-and-naver/">Appier raised a $33M Series C</a></li>
 	<li><a href="https://techcrunch.com/2017/09/04/prowler-io-nabs-13m-for-its-new-approach-to-decision-making-in-ai/">Prowler.io raised $13M</a></li>
 	<li><a href="https://venturebeat.com/2017/09/13/sophia-genetics-raises-30-million-to-help-doctors-diagnose-using-ai-and-genomic-data-analysis/">Sophia Genetics raises $30 million to help doctors diagnose using AI and genomic data</a></li>
</ul>
<h3></h3>
</div>