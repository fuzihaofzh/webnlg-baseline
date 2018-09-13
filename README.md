Scripts to generate the baseline system for the WebNLG Challenge 2017.

See more details [here](http://webnlg.loria.fr/pages/challenge.html).

See run steps: [baseline](http://webnlg.loria.fr/pages/baseline.html).

## Run

- Unpack the archive with the WebNLG dataset into a data-directory folder.
- run `python3 webnlg_baseline_input.py -i data-directory/`
After the preprocessing, an original pair "tripleset-lexicalisation" is modified into a pair of a source and target sequence.

### Original
```xml
<modifiedtripleset>
    <mtriple>Indonesia | leaderName | Jusuf_Kalla</mtriple>
    <mtriple>Bakso | region | Indonesia</mtriple>
    <mtriple>Bakso | ingredient | Noodle</mtriple>
    <mtriple>Bakso | country | Indonesia</mtriple>
</modifiedtripleset>
<lex>
Bakso is a food containing noodles;it is found in Indonesia where Jusuf Kalla is the leader.
</lex>
```
### Modified
source files *.triple:

  >COUNTRY leaderName LEADERNAME FOOD region COUNTRY FOOD ingredient INGREDIENT FOOD country COUNTRY
  
target files *.lex:

  >FOOD is a food containing noodles ; it is found in COUNTRY where LEADERNAME is the leader .

The script writes training and validation files which are used as input to neural generation, as well as reference files for evaluation.
