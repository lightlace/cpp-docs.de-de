---
title: ABSCHNITTE (C/C++) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- SECTIONS
dev_langs:
- C++
helpviewer_keywords:
- SECTIONS .def file statement
ms.assetid: 7b974366-9ef5-4e57-bbcc-73a1df6f8857
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 4c433bf49ee4c56833ac7291bcc4a0f90e32f4e5
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
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
  
 `SECTIONS` kennzeichnet den Anfang einer Liste der Abschnitt `definitions`. Jede `definition` muss in einer separaten Zeile sein. Die `SECTIONS` Schlüsselwort kann in der gleichen Zeile wie der erste `definition` oder in einer vorherigen Zeile. Die DEF-Datei kann eine oder mehrere enthalten `SECTIONS` Anweisungen. Die `SEGMENTS` Schlüsselwort wird als ein Synonym für unterstützt `SECTIONS`.  
  
 Ältere Versionen von Visual C++ unterstützt:  
  
```  
section [CLASS 'classname'] specifier  
```  
  
 Die `CLASS` Schlüsselwort für die Kompatibilität unterstützt wird, wird jedoch ignoriert.  
  
 Genauso wie Abschnittsattribute ist mit der [/SECTION](../../build/reference/section-specify-section-attributes.md) Option.  
  
## <a name="see-also"></a>Siehe auch  
 [Regeln für Moduldefinitionsanweisungen](../../build/reference/rules-for-module-definition-statements.md)