---
title: ABSCHNITTE (C/C++) | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: SECTIONS
dev_langs: C++
helpviewer_keywords: SECTIONS .def file statement
ms.assetid: 7b974366-9ef5-4e57-bbcc-73a1df6f8857
caps.latest.revision: "9"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 9d1564d068f4d69c3190b8bb24a32e7efb01dbef
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/24/2017
---
# <a name="sections-cc"></a>SECTIONS (C/C++)
Stellt einen Abschnitt einer oder mehrerer `definitions` Zugriffsspezifizierer für Abschnitte in der Ausgabedatei des Projekts sind.  
  
```  
SECTIONS  
definitions  
```  
  
## <a name="remarks"></a>Hinweise  
 Jede Definition muss sich in einer separaten Zeile befinden. Die `SECTIONS` Schlüsselwort kann in der gleichen Zeile wie die erste Definition oder in einer vorherigen Zeile sein. Die DEF-Datei kann eine oder mehrere enthalten `SECTIONS` Anweisungen.  
  
 Dies `SECTIONS` Anweisung Attribute für einen oder mehrere Abschnitte in der Bilddatei enthaltenen festgelegt und kann verwendet werden, um die Standardattribute für jeden Abschnitt überschreiben.  
  
 Das Format für `definitions` ist:  
  
 `.section_name specifier`  
  
 wobei `.section_name` ist der Name eines Abschnitts im Programmabbild und `specifier` kann einen oder mehrere der folgenden Zugriffsmodifizierer:  
  
|Modifizierer|Beschreibung|  
|--------------|-----------------|  
|`EXECUTE`|Der Abschnitt ist ausführbar|  
|`READ`|Ermöglicht Lesevorgänge für Daten|  
|`SHARED`|Teilt den Abschnitt für alle Prozesse, die das Image laden|  
|`WRITE`|Ermöglicht Schreibvorgänge für Daten|  
  
 Trennen Sie Namen von Spezifizierer, mit einem Leerzeichen. Zum Beispiel:  
  
```  
SECTIONS  
.rdata READ WRITE  
```  
  
 `SECTIONS`kennzeichnet den Anfang einer Liste der Abschnitt `definitions`. Jede `definition` muss in einer separaten Zeile sein. Die `SECTIONS` Schlüsselwort kann in der gleichen Zeile wie der erste `definition` oder in einer vorherigen Zeile. Die DEF-Datei kann eine oder mehrere enthalten `SECTIONS` Anweisungen. Die `SEGMENTS` Schlüsselwort wird als ein Synonym für unterstützt `SECTIONS`.  
  
 Ältere Versionen von Visual C++ unterstützt:  
  
```  
section [CLASS 'classname'] specifier  
```  
  
 Die `CLASS` Schlüsselwort für die Kompatibilität unterstützt wird, wird jedoch ignoriert.  
  
 Genauso wie Abschnittsattribute ist mit der [/SECTION](../../build/reference/section-specify-section-attributes.md) Option.  
  
## <a name="see-also"></a>Siehe auch  
 [Regeln für Moduldefinitionsanweisungen](../../build/reference/rules-for-module-definition-statements.md)