---
title: Setlocale | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- setlocale_CPP
- vc-pragma.setlocale
dev_langs:
- C++
helpviewer_keywords:
- pragmas, setlocale
- setlocale pragma
ms.assetid: e60b43d9-fbdf-4c4e-ac85-805523a13b86
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: c52697fffb27e6fd25936f3c6566f027cc265c18
ms.sourcegitcommit: d51ed21ab2b434535f5c1d553b22e432073e1478
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/23/2018
---
# <a name="setlocale"></a>setlocale
Definiert das Gebietsschema (Sprache und Land/Region), das beim Übersetzen von Breitzeichenkonstanten und Zeichenfolgenliteralen verwendet werden soll.  
  
## <a name="syntax"></a>Syntax  
  
```  
  
#pragma setlocale( "[locale-string]" )  
```  
  
## <a name="remarks"></a>Hinweise  
 Da der Algorithmus zum Konvertieren von Multibytezeichen in Breitzeichen möglicherweise je nach Gebietsschema variiert oder die Kompilierung möglicherweise in einem anderen Gebietsschema, in dem eine ausführbare Datei ausgeführt wird, stattfindet, bietet dieses Pragma eine Möglichkeit, das Zielgebietsschema zur Kompilierungszeit festzulegen. Dadurch wird sichergestellt, dass die Zeichenfolgen mit Breitzeichen im richtigen Format gespeichert werden.  
  
 Die Standardeinstellung *gebietsschemazeichenfolge* ist "".  
  
 Das Gebietsschema "C" ordnet jedes Zeichen in der Zeichenfolge seinem Wert als  `wchar_t` (kurze ganze Zahl ohne Vorzeichen) zu. Andere gültige Werte für `setlocale` als Einträge, die im gefunden der [Sprachenzeichenfolgen](../c-runtime-library/language-strings.md) Liste. Sie können z. B. Folgendes ausgeben:  
  
```  
#pragma setlocale("dutch")  
```  
  
 Die Möglichkeit, eine Sprachenzeichenfolge auszugeben, hängt von der Codepage- und der Sprachen-ID-Unterstützung Ihres Computers ab.  
  
## <a name="see-also"></a>Siehe auch  
 [Pragma-Direktiven und das __Pragma-Schlüsselwort](../preprocessor/pragma-directives-and-the-pragma-keyword.md)