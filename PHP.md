# PHP

## [Core/Lib/BusinessDocumentCode.php#L4](https://github.com/NeoRazorX/facturascripts/blob/a014af4052e8920927ff0a977bafc37cdb742193/Core/Lib/BusinessDocumentCode.php#L4)

tags: php
note: string formatting

~~~php
...
        $document->codigo = \strtr($sequence->patron, [
            '{ANYO}' => \date('Y', \strtotime($document->fecha)),
            '{DIA}' => \date('d', \strtotime($document->fecha)),
            '{EJE}' => $document->codejercicio,
            '{EJE2}' => \substr($document->codejercicio, -2),
            '{MES}' => \date('m', \strtotime($document->fecha)),
            '{NUM}' => $document->numero,
            '{SERIE}' => $document->codserie,
            '{0NUM}' => \str_pad($document->numero, $sequence->longnumero, '0', \STR_PAD_LEFT),
            '{0SERIE}' => \str_pad($document->codserie, 2, '0', \STR_PAD_LEFT)
        ]);
...
~~~
