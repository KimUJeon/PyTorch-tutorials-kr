파이토치를 이용한 NLP 딥러닝
**********************************
**저자**: `Robert Guthrie <https://github.com/rguthrie3/DeepLearningForNLPInPytorch>`_

This tutorial will walk you through the key ideas of deep learning
programming using Pytorch. Many of the concepts (such as the computation
graph abstraction and autograd) are not unique to Pytorch and are
relevant to any deep learning toolkit out there.
이번 튜토리얼은 파이토치를 이용한 딥 러닝 프로그래밍의 핵심 아이디어를 알려줄 것 입니다.
연산 그래프 추출(computation graph abstraction)이나 autograd 와 같은
많은 개념들이 파이토치에만 있는 것이 아니라 모든 딥 러닝 툴킷 과도 관련이 있습니다.


I am writing this tutorial to focus specifically on NLP for people who
have never written code in any deep learning framework (e.g, TensorFlow,
Theano, Keras, Dynet).It assumes working knowledge of core NLP
problems: part-of-speech tagging, language modeling, etc. It also
assumes familiarity with neural networks at the level of an intro AI
class (such as one from the Russel and Norvig book). Usually, these
courses cover the basic backpropagation algorithm on feed-forward neural
networks, and make the point that they are chains of compositions of
linearities and non-linearities. This tutorial aims to get you started
writing deep learning code, given you have this prerequisite knowledge.

이번엔 딥 러닝 프레임워크(Tensorflow, Theano, Keras, Dynet 등)를
써보지 않은 사람들을 위해 특별히 NLP에만 집중한 튜토리얼입니다.
하지만, 핵심적인 NLP 실무 지식(part-of-speech tagging, language modeling 등)이 요구됩니다.
또한, 입문 수준의 AI 신경망(Russel 이나 Norvig 서적에서 볼 수 있는)에도 친숙해야 합니다.
보통, 이러한 코스들은 기본적인 순방향 신경망의 역전파 알고리즘을 다루고
선형과 비선형으로 구성된 순환이라는 것을 강조합니다. 이 튜토리얼은
여러분들이 전제조건에 대한 지식이 있을 때 딥 러닝 코드를 작성할 수 있도록 만드는것이 목적입니다.


Note this is about *models*, not data. For all of the models, I just
create a few test examples with small dimensionality so you can see how
the weights change as it trains. If you have some real data you want to
try, you should be able to rip out any of the models from this notebook
and use them on it.

데이터가 아니라 '모델'에 대한 것이라는 걸 명심하세요. 저는 훈련할때의 변화를 여러분들이
알아 볼 수 있도록 모든 모델에 대해 작은 규모의 소수의 테스트 예시만 만들것 입니다.
만약 여러분들이 정말 다루고 싶은 데이터가 있다면, 여러분들이 여기에서 아무 모델이나
뜯어 사용하셔도 좋습니다

.. toctree::
    :hidden:

    /beginner/nlp/pytorch_tutorial
    /beginner/nlp/deep_learning_tutorial
    /beginner/nlp/word_embeddings_tutorial
    /beginner/nlp/sequence_models_tutorial
    /beginner/nlp/advanced_tutorial


.. galleryitem:: /beginner/nlp/pytorch_tutorial.py
    :intro: All of deep learning is computations on tensors, which are generalizations of a matrix that can be
            행렬의 일반화가 가능한 모든 딥 러닝은 tensors 에서 계산이 이루어집니다.
.. galleryitem:: /beginner/nlp/deep_learning_tutorial.py
    :intro: Deep learning consists of composing linearities with non-linearities in clever ways. The introduction of non-linearities allows
            딥 러닝은 선형을 훌륭한 방법으로 비 선형으로 구성하는것으로 구성이 된다. 비 선형성의 도입은 허용된다.
.. galleryitem:: /beginner/nlp/word_embeddings_tutorial.py
    :intro: Word embeddings are dense vectors of real numbers, one per word in your vocabulary. In NLP, it is almost always the case that your features are
            단어 임베딩은 여러분들의 사전에 한 단어에 낱말들이 있듯이 실제 숫자들이 밀집된 벡터다. NLP에서 거의 항상 그럴 것 이다.
.. galleryitem:: /beginner/nlp/sequence_models_tutorial.py
    :intro: At this point, we have seen various feed-forward networks. That is, there is no state maintained by the network at all.
            이 부분에서, 우리는 다양한 순방향 신경망을 봤습니다. 즉, 네트워크에 의해 유지되는 상태는 없다는 것 입니다.
.. galleryitem:: /beginner/nlp/advanced_tutorial.py
    :intro: Dynamic versus Static Deep Learning Toolkits. Pytorch is a *dynamic* neural network kit.
            동적 vs 정적 딥 러닝 툴 킷. Pytorch 는 '동적'인 신경망 킷 입니다.

.. raw:: html

    <div style='clear:both'></div>
