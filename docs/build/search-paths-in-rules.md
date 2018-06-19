---
title: Suchpfade in Regeln | Microsoft Docs
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
ms.openlocfilehash: 25127377f20de3cb7c7b55e275692eefbf077067
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
ms.locfileid: "32380400"
---
# <a name="search-paths-in-rules"></a>Suchpfade in Regeln
```  
{frompath}.fromext{topath}.toext:  
   commands  
```  
  
## <a name="remarks"></a>Hinweise  
 Eine Rückschlussregel mithilfe eines gilt für eine Abhängigkeit nur dann, wenn genau in Abhängigkeit der angegebenen Pfade Rückschlussregel Pfade entsprechen. Geben Sie die abhängigen Verzeichnis in *Frompath* und das Zielverzeichnis im *Topath*; sind keine Leerzeichen zulässig. Geben Sie nur ein Pfad für jede Erweiterung ein. Ein Pfad auf eine Erweiterung muss einen Pfad auf dem anderen. Um das aktuelle Verzeichnis anzugeben, verwenden Sie einen Punkt (.) oder leere geschweifte Klammern ({}). Makros können repräsentieren *Frompath* und *Topath*; sie werden aufgerufen, während der vorverarbeitung.  
  
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