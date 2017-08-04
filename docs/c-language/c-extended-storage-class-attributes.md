---
title: Erweiterte C-Speicherklassenattribute | Microsoft-Dokumentation
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
helpviewer_keywords:
- __declspec keyword [C]
- extended attributes
- extended storage-class attributes
- storage class specifiers, C storage classes
ms.assetid: 2580735c-f5bf-46ab-9468-0696893d82be
caps.latest.revision: 9
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
ms.translationtype: Human Translation
ms.sourcegitcommit: d6eb43b2e77b11f4c85f6cf7e563fe743d2a7093
ms.openlocfilehash: e79b08ebba48221e8666ced75875a68f06bf2df3
ms.contentlocale: de-de
ms.lasthandoff: 05/18/2017

---
# <a name="c-extended-storage-class-attributes"></a>C-Speicherklassenattribute (erweitert)
**Microsoft-spezifisch**  
  
 Weitere aktuelle Informationen über dieses Thema finden Sie unter [__declspec (C++-Verweis)](../cpp/declspec.md).  
  
 Die erweiterte Attributsyntax vereinfacht und standardisiert Microsoft-spezifische Erweiterungen der Programmiersprache C. Zu den Speicherklassenattributen, die die erweiterte Attributsyntax verwenden, gehören Thread, naked, dllimport und dllexport.  
  
 Der erweiterte Attributsyntax zur Bezeichnung von Speicherklasseninformation verwendet das _declspec-Schlüsselwort, welches angibt, dass eine Instanz eines gegebenen Typs mit einem Microsoft-spezifischen Speicherklassenattribut (thread, naked, dllimport oder dllexport) gespeichert werden muss. Beispiele anderer Speicherklassenmodifizierer umfassen die statischen und externen Schlüsselwörter. Allerdings sind diese Schlüsselwörter Teil des ANSI C-Standards und werden somit nicht von der erweiterten Attributsyntax abgedeckt.  
  
## <a name="syntax"></a>Syntax  
 *storage-class-specifier*:  
 `__declspec` ( *extended-decl-modifier-seq* ) /* Microsoft-spezifisch \*/  
  
 *extended-decl-modifier-seq*:  
 *extended-decl-modifier* opt  
  
 *extended-decl-modifier-seq extended-decl-modifier*  
  
 *extended-decl-modifier*:  
 **thread**  
  
 **naked**  
  
 **dllimport**  
  
 `dllexport`  
  
 Die Deklarationsmodifizierer sind durch Leerzeichen getrennt. Beachten Sie, dass *extended-decl-modifier-seq* leer sein darf. „__declspec“ hat in diesem Fall keine Auswirkungen.  
  
 Die Speicherklassenattribute thread, naked, dllimport und dllexport sind nur Eigenschaften für die Daten- oder Funktionsdeklaration, auf die sie angewendet werden. Sie definieren nicht die Typattribute der Funktion selbst neu. Das Threadattribut wirkt sich nur auf Daten aus. Das naked-Attribut wirkt sich nur auf Funktionen aus. Die Attribute dllimport und dllexport wirken sich auf Funktionen und Daten aus.  
  
 **Ende Microsoft-spezifisch**  
  
## <a name="see-also"></a>Siehe auch  
 [Deklarationen und Typen](../c-language/declarations-and-types.md)
