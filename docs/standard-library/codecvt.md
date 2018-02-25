---
title: '&lt;codecvt&gt; | Microsoft-Dokumentation'
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- codecvt
- <codecvt>
dev_langs:
- C++
helpviewer_keywords:
- codecvt header
ms.assetid: d44ee229-00d5-4761-9b48-0c702122789d
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: ea9bf0c81e66f875a3a94ab1e5783bcd4de91edd
ms.sourcegitcommit: d51ed21ab2b434535f5c1d553b22e432073e1478
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/23/2018
---
# <a name="ltcodecvtgt"></a>&lt;codecvt&gt;
Definiert mehrere Vorlagenklassen, die Objekte anhand der Vorlagenklasse [codecvt](../standard-library/codecvt-class.md) beschreiben. Diese Objekte können als [Gebietsschemafacets](../standard-library/locale-class.md#facet_class) dienen, die Konvertierungen zwischen einer Sequenz von Werten des Typs `Elem` und einer Sequenz von Werten des Typs `char` steuern.  
  
## <a name="syntax"></a>Syntax  
  
```  
#include <codecvt>  
  
```  
  
## <a name="remarks"></a>Hinweise  
 Die in diesem Header deklarierten Gebietsschemafacets führen Konvertierungen zwischen verschiedenen Zeichencodierungen durch. Bei Breitzeichen (innerhalb des Programms als ganze Zahlen mit fester Größe gespeichert):  
  
-   UCS-4 ist innerhalb des Programms codierter Unicode (ISO 10646)  
  
-   UCS-4 ist innerhalb des Programms als 32-Bit-Integer codierter Unicode (ISO 10646).  
  
-   UCS-2 ist innerhalb des Programms codierter Unicode  
  
-   UCS-2 ist innerhalb des Programms als 16-Bit-Integer codierter Unicode.  
  
-   UTF-16 ist innerhalb des Programms als eines von beidem codierter Unicode  
  
-   UTF-16 ist innerhalb des Programms als eine oder zwei 16-Bit-Integer codierter Unicode. (Hinweis: Dies erfüllt nicht alle Anforderungen einer gültigen Breitzeichencodierung für Standard C oder Standard C++. Es ist aber als solches weit verbreitet.)  
  
 Bei Bytestreams (in einer Datei gespeichert, als Bytesequenz übertragen oder innerhalb des Programms in einem Array von `char` gespeichert):  
  
-   UTF-8 ist Unicode-codiert  
  
-   UTF-8 ist innerhalb eines Bytestreams als eine oder mehrere 8-Bit-Bytes mit deterministischer Bytereihenfolge Unicode-codiert.  
  
-   UTF-16LE ist Unicode-codiert  
  
-   UTF-16LE ist in einem Bytestream als UTF-16 Unicode-codiert, wobei jeder 16-Bit-Integer als zwei 8-Bit-Bytes dargestellt wird (das weniger signifikante Byte zuerst).  
  
-   UTF-16BE ist Unicode-codiert  
  
-   UTF-16BE ist in einem Bytestream als UTF-16 Unicode-codiert, wobei jeder 16-Bit-Integer als zwei 8-Bit-Bytes dargestellt wird (das signifikantere Byte zuerst).  
  
### <a name="enumerations"></a>Enumerationen  
  
|||  
|-|-|  
|[codecvt_mode](../standard-library/codecvt-enums.md#codecvt_mode)|Gibt die Konfigurationsinformationen für Gebietsschemafacets an.|  
  
### <a name="classes"></a>Klassen  
  
|||  
|-|-|  
|[codecvt_utf8](codecvt-utf8-class.md)|Stellt ein Gebietsschemafacet dar, das eine Konvertierung durchführt zwischen Breitzeichen, die als UCS-2 oder UCS-4 codiert sind, und einem Bytestream, der als UTF-8 codiert ist.|  
|[codecvt_utf8_utf16](codecvt-utf8-utf16-class.md)|Stellt ein Gebietsschemafacet dar, das eine Konvertierung durchführt zwischen Breitzeichen, die als UTF-16 codiert sind, und einem Bytestream, der als UTF-8 codiert ist.|  
|[codecvt_utf16](codecvt-utf16-class.md)|Stellt ein Gebietsschemafacet dar, das eine Konvertierung durchführt zwischen Breitzeichen, die als UCS-2 oder UCS-4 codiert sind, und einem Bytestream, der als UTF-16LE oder UTF-16BE codiert ist.|  

  
## <a name="requirements"></a>Anforderungen  
 **Header:** \<codecvt>  
  
 **Namespace:** stdt  
  
## <a name="see-also"></a>Siehe auch  
 [Headerdateienreferenz](../standard-library/cpp-standard-library-header-files.md)




