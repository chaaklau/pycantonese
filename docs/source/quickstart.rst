.. _quickstart:

Quickstart
==========

After you have downloaded and installed PyCantonese (see :ref:`download_install`),
import the package ``pycantonese`` in your Python interpreter:

.. code-block:: python

    >>> import pycantonese

No errors? Great! Now you're ready to proceed.

1. Word segmentation

.. code-block:: python

    >>> pycantonese.segment("廣東話好難學？")  # Is Cantonese difficult to learn?
    ['廣東話', '好', '難', '學', '？']

2. Conversion from Cantonese characters to Jyutping

.. code-block:: python

    >>> pycantonese.characters_to_jyutping('香港人講廣東話')  # Hongkongers speak Cantonese
    [('香港人', 'hoeng1gong2jan4'), ('講', 'gong2'), ('廣東話', 'gwong2dung1waa2')]

3. Finding all verbs in the HKCanCor corpus

   In this example,
   we search for the regular expression ``'^V'`` for all words whose
   part-of-speech tag begins with "V" in the original HKCanCor annotations:

.. code-block:: python

    >>> corpus = pycantonese.hkcancor() # get HKCanCor
    >>> all_verbs = corpus.search(pos='^V')
    >>> len(all_verbs)  # number of all verbs
    29726
    >>> all_verbs[:10]  # print 10 results
    [Token(word='去', pos='V', jyutping='heoi3', mor=None, gra=None),
     Token(word='去', pos='V', jyutping='heoi3', mor=None, gra=None),
     Token(word='旅行', pos='VN', jyutping='leoi5hang4', mor=None, gra=None),
     Token(word='有冇', pos='V1', jyutping='jau5mou5', mor=None, gra=None),
     Token(word='要', pos='VU', jyutping='jiu3', mor=None, gra=None),
     Token(word='有得', pos='VU', jyutping='jau5dak1', mor=None, gra=None),
     Token(word='冇得', pos='VU', jyutping='mou5dak1', mor=None, gra=None),
     Token(word='去', pos='V', jyutping='heoi3', mor=None, gra=None),
     Token(word='係', pos='V', jyutping='hai6', mor=None, gra=None),
     Token(word='係', pos='V', jyutping='hai6', mor=None, gra=None)]

4. Parsing Jyutping for the onset, nucleus, coda, and tone

.. code-block:: python

    >>> pycantonese.parse_jyutping('gwong2dung1waa2')  # 廣東話
    [Jyutping(onset='gw', nucleus='o', coda='ng', tone='2'),
     Jyutping(onset='d', nucleus='u', coda='ng', tone='1'),
     Jyutping(onset='w', nucleus='aa', coda='', tone='2')]

Looking for more functionality?
Please use the documentation menu on the left.
