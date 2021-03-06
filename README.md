# sylbreak
Syllable segmenation is an important preprocess for many natural language processing (NLP) such as romanization, transliteration and graphame-to-phoneme (g2p) conversion.

"sylbreak" is a syllable segmentation tool for Myanmar language (Burmese) text encoded with Unicode (e.g. Myanmar3, Padauk).
I used only one short line of regular expression (RE) as follow:
```perl
$line =~ s/((?<!$ssSymbol)[$myConsonant](?![$aThat$ssSymbol])|[$enChar$otherChar])/$sep$1/g;
```
Here, the point is (a consonant not after a subscript symbol AND not followed by a-That character or a subscript symbol)

Here, variables are declared as follows:

```perl
my $myConsonant = "က-အ";
my $enChar = "a-zA-Z0-9";
my $otherChar = "ဣဤဥဥဧဩဪဿ၌၍၏၀-၉၊။!-\/:-\@\[-`{-~\\s";
my $ssSymbol = "္";
my $aThat = "်";
```
If you use shell (sylbreak.sh), perl (sylbreak.pl) and python (sylbreak.py) scripts, no need to make installation.
I plan to update/code *sylbreak* with some more programming languages such as C++, Ruby in the near future.

Enjoy syllable breaking!

Ye@Lab
