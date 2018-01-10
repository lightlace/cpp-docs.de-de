---
title: Suchpfade in Regeln | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- search paths in NMAKE inference rules
- inference rules in NMAKE
- rules, inference
ms.assetid: 38feded6-536d-425d-bf40-fff3173a5506
caps.latest.revision: "7"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 3d62ab17831afec4cc1f8e424766925529dd8e1f
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
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