---
title: "Verknüpfung in Namen mit Dateigültigkeitsbereich | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
dev_langs:
- C++
helpviewer_keywords:
- scope [C++], linkage rules
- linkage [C++], scope linkage rules
- names [C++], scope linkage rules
- static modifier, file scope
- static names and file scope
- file scope [C++]
- declarations [C++], external
- external linkage, scope linkage rules
- static variables, external declarations
ms.assetid: 38d3fa5e-1861-466e-a590-84b86f7b184e
caps.latest.revision: 8
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
ms.translationtype: HT
ms.sourcegitcommit: 6ffef5f51e57cf36d5984bfc43d023abc8bc5c62
ms.openlocfilehash: c4d33071426eac428cc1728aa13b403953a99389
ms.contentlocale: de-de
ms.lasthandoff: 09/25/2017

---
# <a name="linkage-in-names-with-file-scope"></a>Verknüpfung in Namen mit Dateibereich
Die folgenden Verknüpfungsregeln gelten für Namen (außer `typedef` und Enumeratornamen) mit dem Dateibereich:  
  
-   Wenn Sie ein Namen als explizit deklariert wird **statische**, er über interne Verknüpfung und identifiziert ein Programmelement in seiner eigenen Übersetzungseinheit.  
  
-   Enumeratornamen und `typedef`-Namen haben keine Verknüpfung.  
  
-   Alle anderen Namen mit Dateigültigkeitsbereich haben externe Verknüpfung.  
  
 **Microsoft-spezifisch**  
  
-   Wenn ein Funktionsname mit Dateigültigkeitsbereich explizit, als deklariert wird **Inline**, hat eine externe Bindung, wenn die Funktion instanziiert wird oder dessen Adresse verwiesen wird. Daher kann eine Funktion mit Dateigültigkeitsbereich entweder eine interne oder eine externe Verknüpfung besitzen.  
  
 **Ende Microsoft-spezifisch**  
  
 In folgenden Fällen verfügt eine Klasse über interne Verknüpfung:  
  
-   Sie verwendet keine C++-Funktionalität (z. B. Zugriffssteuerung, Memberfunktionen, Konstruktoren, Destruktoren usw.).  
  
-   Sie wird nicht in der Deklaration eines anderen Namens mit externer Verknüpfung verwendet. Diese Einschränkung bedeutet, dass Objekte vom Klassentyp, die an Funktionen mit externer Verknüpfung übergeben werden, eine externe Verknüpfung der Klasse verursachen.  
  
## <a name="see-also"></a>Siehe auch  
 [Programm und Verknüpfung](../cpp/program-and-linkage-cpp.md)
