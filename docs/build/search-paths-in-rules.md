---
title: Suchpfade in Regeln | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- search paths in NMAKE inference rules
- inference rules in NMAKE
- rules, inference
ms.assetid: 38feded6-536d-425d-bf40-fff3173a5506
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: c96ee89367c3ac289dffde9029cb2b5d3cdc3e89
ms.sourcegitcommit: 92f2fff4ce77387b57a4546de1bd4bd464fb51b6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/17/2018
ms.locfileid: "45703975"
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