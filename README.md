# Opinioned Quarto letter template for the ASU BiG research group

This is a Quarto template that assists you in writing a letter.

The template is based on the LaTex `letter` class, with a customized layout including a logo at the upper left, a name block on the upper right, and an address block at the bottom left of the first page.

This template is the quarto version of the [original `rmd` letter template](https://github.com/juliantao/bigrmd/tree/master/inst/rmarkdown/templates/Letter) for the same research group. Original inspirations were drawn from [Rob Hyndman's MonashEBSTemplates](https://github.com/robjhyndman/MonashEBSTemplates/tree/master/inst/rmarkdown/templates/Letter). I also burrowed some ideas from the [quarto-letter extension](https://github.com/mcanouil/quarto-letter).


## Creating a New Letter

You can use this as a template to create a letter with the ASU default. To do this, use the following command:

```bash
quarto use template juliantao/qletter
```

This will install the extension and create an example qmd file. You'll need to modify the various fields in the YAML header and replace the placeholder logo with your own logo. 

After rendering, the pdf file will be saved to the `_output` folder.

An

## Usage

To use the format, you can use the format names `qletter-pdf`. For example:

```bash
quarto render letter.qmd --to qletter-pdf
```

or in your document yaml

```yaml
format: qletter-pdf
```

You can view a preview of the rendered template at <https://github.com/juliantao/quarto-asce/blob/main/style-guide/asce-template.pdf>.

## YAML header and logo file 

```yaml
---
fromname: Sender name
fromqualifications: PhD
fromtitle: Professor
fromWWW: sender.com
fromemail: sender@sender.com
fromphone: (000) 000 000
fromdepartment: Sender Department 
frominstitute: Sender Institution 
fromaddress: Sender Address in one line 
fromsignature: signature
fromlogo: logo
toname: Recipient
toaddress: |
  | Recipient address line 1 
  | Recipient address line 2
subject: Subject Line
opening: Dear Recipient, 
closing: Best regards,
cc:
  - CC 1 
  - CC 2
encl:
  - Enclosure 1
  - Enclosure 2
ps: |
  p.s.: something else 
spacing: 1.2
format: qletter-pdf
---

```

1. Sender fields starts with `from`
2. Recipient fields starts with `to`
3. You can also set a different `fontfamily`,  `fontsize`, and `spacing`. The default fontfamily is `Roboto` and the size is `12pt`
4. The `fromWWW` field is your website **without the starting string of `https://`**
5. Save a copy of your logo and signature files in the directory, **please use a pdf format**
6. The recipient's address can have more than two lines in the `toaddress` field, just add more lines with the syntax `- address`
7. `cc`, `encl`, and `ps` fields are optional.
