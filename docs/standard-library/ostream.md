---
title: '&lt;ostream&gt; | Microsoft-Dokumentation'
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- <ostream>
- ostream/std::<ostream>
- std::<ostream>
dev_langs: C++
helpviewer_keywords: ostream header
ms.assetid: 90c3b6fb-57cd-4ae7-99b8-8512f24a67d2
caps.latest.revision: "20"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: d4805086fb3d63d16f5f9ce6bf3b9e900b436569
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="ltostreamgt"></a>&lt;ostream&gt;
Definiert die Vorlagenklasse [basic_ostream](../standard-library/basic-ostream-class.md), die Einfügungen für die iostreams vermittelt. Der Header definiert auch mehrere verwandte Manipulatoren. Dieser Header wird in der Regel von einem der anderen iostreams-Header für Sie eingefügt. Sie müssen ihn nur selten direkt einfügen.)  
  
## <a name="syntax"></a>Syntax  
  
```  
#include <ostream>  
  
```  
  
### <a name="typedefs"></a>Typedefs  
  
|||  
|-|-|  
|[ostream](../standard-library/ostream-typedefs.md#ostream)|Erstellt einen Typ aus `basic_ostream`, der auf `char` spezialisiert ist, und `char_traits`, spezialisiert auf `char`.|  
|[wostream](../standard-library/ostream-typedefs.md#wostream)|Erstellt einen Typ aus `basic_ostream`, der auf `wchar_t` spezialisiert ist, und `char_traits`, spezialisiert auf `wchar_t`.|  
  
### <a name="manipulators"></a>Manipulatoren  
  
|||  
|-|-|  
|[endl](../standard-library/ostream-functions.md#endl)|Beendet eine Zeile und leert den Puffer.|  
|[ends](../standard-library/ostream-functions.md#ends)|Beendet eine Zeichenfolge.|  
|[flush](../standard-library/ostream-functions.md#flush)|Leert den Puffer.|  
|[swap](../standard-library/ostream-functions.md#swap)|Tauscht die Werte des linken `basic_ostream`-Objektparameters gegen diejenigen des rechten `basic_ostream`-Objektparameters aus.|  
  
### <a name="operators"></a>Operatoren  
  
|||  
|-|-|  
|[operator<<](../standard-library/ostream-operators.md#op_lt_lt)|Schreibt verschiedene Typen in den Stream.|  
  
### <a name="classes"></a>Klassen  
  
|||  
|-|-|  
|[basic_ostream](../standard-library/basic-ostream-class.md)|Die Vorlagenklasse beschreibt ein Objekt, das das Einfügen von Elementen und codierten Objekten in einen Streampuffer steuert.|  
  
## <a name="see-also"></a>Siehe auch  
 [Headerdateienreferenz](../standard-library/cpp-standard-library-header-files.md)   
 [Threadsicherheit in der C++-Standardbibliothek](../standard-library/thread-safety-in-the-cpp-standard-library.md)   
 [iostream-Programmierung](../standard-library/iostream-programming.md)   
 [iostreams-Konventionen](../standard-library/iostreams-conventions.md)



