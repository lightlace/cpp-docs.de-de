---
title: Verwenden von Extraktionsoperatoren | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- extraction operators
- '>> operator, extraction operators'
- operators [C++], extraction
ms.assetid: a961e1a9-4897-41de-b210-89d5b2d051ae
caps.latest.revision: 8
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
translationtype: Machine Translation
ms.sourcegitcommit: 85c900f2263ae1c1089478badc85388e3b5e8548
ms.openlocfilehash: e5dcc1e57b807ee7ff7b4292f31563d4041c0bdd
ms.lasthandoff: 02/24/2017

---
# <a name="using-extraction-operators"></a>Verwenden von Extraktionsoperatoren
Mit dem für alle C++-Standarddatentypen vorprogrammierten Extraktionsoperator (`>>`) können Bytes am einfachsten aus einem Eingabestreamobjekt abgerufen werden.  
  
 Bei Extraktionsoperatoren für die Eingabe von formatiertem Text werden eingehende Datenwerte mit Leerzeichen voneinander getrennt. Das ist ungünstig, wenn ein Textfeld mehrere Wörter enthält oder wenn Zahlen durch Kommas voneinander getrennt werden. In solch einem Fall kann die Memberfunktion [istream::getline](../standard-library/basic-istream-class.md#basic_istream__getline) für nicht formatierte Eingabe zum Lesen eines Textblocks mit Leerzeichen verwendet und anschließend der Textblock mit speziellen Funktionen analysiert werden. Alternativ kann auch eine Eingabestreamklasse mit einer Memberfunktion wie `GetNextToken` abgeleitet werden, die zum Extrahieren und Formatieren von Zeichendaten istream-Member aufrufen kann.  
  
## <a name="see-also"></a>Siehe auch  
 [Eingabestreams](../standard-library/input-streams.md)


