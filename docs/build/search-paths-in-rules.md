---
title: Suchpfade in Regeln
ms.date: 11/04/2016
helpviewer_keywords:
- search paths in NMAKE inference rules
- inference rules in NMAKE
- rules, inference
ms.assetid: 38feded6-536d-425d-bf40-fff3173a5506
ms.openlocfilehash: 26b02fa76920f0d0ff380dacd5aa76cfe8e92c79
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50649968"
---
# <a name="search-paths-in-rules"></a>Suchpfade in Regeln

```
{frompath}.fromext{topath}.toext:
   commands
```

## <a name="remarks"></a>Hinweise

Eine Rückschlussregel gilt für eine Abhängigkeit, nur dann, wenn genau der Abhängigkeit angegebenen Pfade Rückschlussregel Pfade entsprechen. Geben Sie Verzeichnis in der abhängigen *Frompath* und das Verzeichnis des Ziels in *Topath*; keine Leerzeichen sind zulässig. Geben Sie nur einen Pfad für jede Erweiterung ein. Ein Pfad auf eine Erweiterung ist ein Pfad auf dem anderen erforderlich. Um das aktuelle Verzeichnis anzugeben, verwenden Sie einen Punkt (.) oder leeren geschweiften Klammern ({}). Makros können repräsentieren *Frompath* und *Topath*; sie werden aufgerufen, während der vorverarbeitung.

## <a name="example"></a>Beispiel

### <a name="code"></a>Code

```
{dbi\}.cpp{$(ODIR)}.obj::
        $(CC) $(CFLAGS) $(YUDBI) $<

{ilstore\}.cpp{$(ODIR)}.obj::
        $(CC) $(CFLAGS) $<

{misc\}.cpp{$(ODIR)}.obj::
        $(CC) $(CFLAGS) $(YUPDB) $<

{misc\}.c{$(ODIR)}.obj::
        $(CC) $(CFLAGS) $<

{msf\}.cpp{$(ODIR)}.obj::
        $(CC) $(CFLAGS) $<

{bsc\}.cpp{$(ODIR)}.obj::
        $(CC) $(CFLAGS) $(YUPDB) $<

{mre\}.cpp{$(ODIR)}.obj::
        $(CC) $(CFLAGS) $(YUPDB) $<

{namesrvr\}.cpp{$(ODIR)}.obj::
        $(CC) $(CFLAGS) $(YUPDB) $<

{src\cvr\}.cpp{$(ODIR)}.obj::
        $(CC) $(CFLAGS) $<
```

## <a name="see-also"></a>Siehe auch

[Definieren einer Regel](../build/defining-a-rule.md)