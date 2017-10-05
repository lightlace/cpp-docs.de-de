---
title: wbuffer_convert-Klasse | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- xlocmon/stdext::cvt::wbuffer_convert
dev_langs:
- C++
helpviewer_keywords:
- wbuffer_convert class
ms.assetid: 4a56f9bf-4138-4612-b516-525fea401358
caps.latest.revision: 20
author: corob-msft
ms.author: corob
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: MT
ms.sourcegitcommit: 65f4e356ad0d46333b0d443d0fd6ac0b9f2b6f58
ms.openlocfilehash: 502b532fc0c2dfe4ba19844b35e6c301c2764a8b
ms.contentlocale: de-de
ms.lasthandoff: 10/03/2017

---
# <a name="wbufferconvert-class"></a>wbuffer_convert-Klasse
Beschreibt einen Streampuffer, der die Übertragung von Elementen in einen bzw. aus einem Streampuffer steuert.  
  
## <a name="syntax"></a>Syntax  
  
```
template <class Codecvt, class Elem = wchar_t, class Traits = std::char_traits<Elem>>
class wbuffer_convert
 : public std::basic_streambuf<Elem, Traits>
```  
  
#### <a name="parameters"></a>Parameter  
  
|Parameter|Beschreibung|  
|---------------|-----------------|  
|`Codecvt`|Das Facet [locale](../standard-library/locale-class.md), das das Konvertierungsobjekt darstellt.|  
|`Elem`|Der Breitzeichen-Elementtyp.|  
|`Traits`|Die mit *Elem* verknüpften Merkmale.|  
  
## <a name="remarks"></a>Hinweise  
 Die Vorlagenklasse beschreibt einen Streampuffer, der die Übertragung der Elemente des Typs `_Elem` beschreibt, dessen Zeichenmerkmale durch die Klasse `Traits` beschrieben werden, und zwar zu und von einem Bytestreampuffer des Typs `std::streambuf`.  
  
 Konvertierung zwischen einer Sequenz von `Elem`-Werten und Multibytesequenzen erfolgt durch ein Objekt der Klasse `Codecvt<Elem, char, std::mbstate_t>`, das die Anforderungen des Facets `std::codecvt<Elem, char, std::mbstate_t>` für die Standardcodekonvertierung erfüllt.  
  
 Ein Objekt dieser Vorlagenklasse speichert:  
  
-   Ein Zeiger auf den entsprechenden zugrunde liegenden Bytestreampuffer  
  
-   Ein Zeiger auf das zugeordnete Konvertierungsobjekt (das freigegeben wird, wenn das [wbuffer_convert](../standard-library/wbuffer-convert-class.md)-Objekt

