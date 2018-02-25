---
title: Verwenden von Extraktionsoperatoren | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- extraction operators [C++]
- '&gt;&gt; operator [C++], extraction operators'
- operators [C++], extraction
ms.assetid: a961e1a9-4897-41de-b210-89d5b2d051ae
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: bb9e62ffd1e466fd220012717e278b79bbce3e1f
ms.sourcegitcommit: d51ed21ab2b434535f5c1d553b22e432073e1478
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/23/2018
---
# <a name="using-extraction-operators"></a>Verwenden von Extraktionsoperatoren
Mit dem für alle C++-Standarddatentypen vorprogrammierten Extraktionsoperator (`>>`) können Bytes am einfachsten aus einem Eingabestreamobjekt abgerufen werden.  
  
 Bei Extraktionsoperatoren für die Eingabe von formatiertem Text werden eingehende Datenwerte mit Leerzeichen voneinander getrennt. Das ist ungünstig, wenn ein Textfeld mehrere Wörter enthält oder wenn Zahlen durch Kommas voneinander getrennt werden. In solch einem Fall kann die Memberfunktion [istream::getline](../standard-library/basic-istream-class.md#getline) für nicht formatierte Eingabe zum Lesen eines Textblocks mit Leerzeichen verwendet und anschließend der Textblock mit speziellen Funktionen analysiert werden. Alternativ kann auch eine Eingabestreamklasse mit einer Memberfunktion wie `GetNextToken` abgeleitet werden, die zum Extrahieren und Formatieren von Zeichendaten istream-Member aufrufen kann.  
  
## <a name="see-also"></a>Siehe auch  
 [Eingabestreams](../standard-library/input-streams.md)

