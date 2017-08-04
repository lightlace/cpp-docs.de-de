---
title: Umwandlungsoperatoren | Microsoft-Dokumentation
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
- cast operators
- type casts, operators
- operators [C++], cast
- type conversion, cast operators
ms.assetid: 43b90bbd-39ef-43e6-ae5d-e8a67a01de40
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
ms.translationtype: Human Translation
ms.sourcegitcommit: d6eb43b2e77b11f4c85f6cf7e563fe743d2a7093
ms.openlocfilehash: c1d8315270f6b69629eca55e7aa1c6198f414117
ms.contentlocale: de-de
ms.lasthandoff: 05/18/2017

---
# <a name="cast-operators"></a>Umwandlungsoperatoren
Eine Typumwandlung stellt eine Möglichkeit zum expliziten Konvertieren des Typs eines Objekts in einer bestimmten Situation bereit.  
  
## <a name="syntax"></a>Syntax  
 *cast-expression*:  
 *unary-expression*  
  
 **(**  *type-name*  **)**  *cast-expression*  
  
 Der Compiler behandelt *cast-expression* als *type-name*-Typ, nachdem eine Typumwandlung vorgenommen wurde. Umwandlungen können verwendet werden, um Objekte eines beliebigen skalaren Typs in einen oder aus einem anderen skalaren Typ zu konvertieren. Explizite Typumwandlungen werden durch dieselben Regeln eingeschränkt, die die Auswirkungen von impliziten Konvertierungen bestimmen, die unter [Zuweisungskonvertierungen](../c-language/assignment-conversions.md) erläutert werden. Zusätzliche Einschränkungen für Typumwandlungen ergeben sich möglicherweise aus den tatsächlichen Größen oder der Darstellung bestimmter Typen. Weitere Informationen zu den tatsächlichen Größen ganzzahliger Typen finden Sie unter [Speicherung von einfachen Typen](../c-language/storage-of-basic-types.md). Weitere Informationen zu Typumwandlungen finden Sie unter [Typumwandlungskonvertierungen](../c-language/type-cast-conversions.md).  
  
## <a name="see-also"></a>Siehe auch  
 [Umwandlungsoperator](../cpp/cast-operator-parens.md)
