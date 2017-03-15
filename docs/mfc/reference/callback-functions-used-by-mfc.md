---
title: "Von MFC verwendete Rückruffunktionen | Microsoft-Dokumentation"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- vc.mfc.functions
dev_langs:
- C++
helpviewer_keywords:
- callback functions, MFC
- MFC, callback functions
- functions [C++], callback
- callback functions
ms.assetid: b2a6857c-fdd3-45ec-8fd8-2e71fac77582
caps.latest.revision: 11
author: mikeblome
ms.author: mblome
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
translationtype: Machine Translation
ms.sourcegitcommit: 040985df34f2613b4e4fae29498721aef15d50cb
ms.openlocfilehash: b4d104fa76347da43c84611672f843511f0f3725
ms.lasthandoff: 02/24/2017

---
# <a name="callback-functions-used-by-mfc"></a>Von MFC verwendete Rückruffunktionen
Drei Callback-Funktionen werden in der Microsoft Foundation Class-Bibliothek angezeigt. Eine Beschreibung der Callback-Funktionen, die übergeben werden [CDC:: EnumObjects](../../mfc/reference/cdc-class.md#enumobjects), [CDC:: graystring](../../mfc/reference/cdc-class.md#graystring), und [CDC:: setabortproc](../../mfc/reference/cdc-class.md#setabortproc) folgt in diesem Thema. Finden Sie für die allgemeine Verwendung Rückruffunktionen im Abschnitt "Hinweise" diese Memberfunktionen. Beachten Sie, dass alle Rückruffunktionen vor der Rückgabe auf Windows, da Ausnahmen hinweg Rückruf ausgelöst werden, können nicht MFC-Ausnahmen abfangen müssen. Weitere Informationen zu Ausnahmen finden Sie im Artikel [Ausnahmen](../../mfc/exception-handling-in-mfc.md).  
  
## <a name="see-also"></a>Siehe auch  
 [Strukturen, Stile, Rückrufe und Meldungszuordnungen](../../mfc/reference/structures-styles-callbacks-and-message-maps.md)


