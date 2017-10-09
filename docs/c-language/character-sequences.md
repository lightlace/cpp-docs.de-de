---
title: Zeichenfolgen | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-language
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
ms.assetid: 1e6961a9-150e-4c13-b427-9af4b6a1fb7a
caps.latest.revision: 7
author: mikeblome
ms.author: mblome
manager: ghogen
ms.translationtype: HT
ms.sourcegitcommit: 16d1bf59dfd4b3ef5f037aed9c0f6febfdf1a2e8
ms.openlocfilehash: c097f213d790a992d12a8c358282a5340fce52c4
ms.contentlocale: de-de
ms.lasthandoff: 10/09/2017

---
# <a name="character-sequences"></a>Zeichensequenzen
**ANSI 3.8.2** Die Zuordnung der Quelldatei-Zeichenfolgen  
  
 Präprozessoranweisungen verwenden den gleichen Zeichensatz wie Quelldateianweisungen, mit der Ausnahme, dass Escapesequenzen nicht unterstützt werden.  
  
 Um einen Pfad für eine Includedatei anzugeben, verwenden Sie nur einen umgekehrten Schrägstrich:  
  
```  
#include "path1\path2\myfile"  
```  
  
 Im Quellcode sind zwei umgekehrte Schrägstriche erforderlich:  
  
```  
fil = fopen( "path1\\path2\\myfile", "rt" );  
```  
  
## <a name="see-also"></a>Siehe auch  
 [Präprozessoranweisungen](../c-language/preprocessing-directives.md)
