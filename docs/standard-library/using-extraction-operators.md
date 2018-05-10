---
title: Verwenden von Extraktionsoperatoren | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- extraction operators [C++]
- '&gt;&gt; operator [C++], extraction operators'
- operators [C++], extraction
ms.assetid: a961e1a9-4897-41de-b210-89d5b2d051ae
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 96dc02c8bcd82c5b26d3cef71aa2085913ea259d
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/08/2018
---
# <a name="using-extraction-operators"></a>Verwenden von Extraktionsoperatoren

Mit dem für alle C++-Standarddatentypen vorprogrammierten Extraktionsoperator (`>>`) können Bytes am einfachsten aus einem Eingabestreamobjekt abgerufen werden.

Bei Extraktionsoperatoren für die Eingabe von formatiertem Text werden eingehende Datenwerte mit Leerzeichen voneinander getrennt. Das ist ungünstig, wenn ein Textfeld mehrere Wörter enthält oder wenn Zahlen durch Kommas voneinander getrennt werden. In solch einem Fall kann die Memberfunktion [istream::getline](../standard-library/basic-istream-class.md#getline) für nicht formatierte Eingabe zum Lesen eines Textblocks mit Leerzeichen verwendet und anschließend der Textblock mit speziellen Funktionen analysiert werden. Alternativ kann auch eine Eingabestreamklasse mit einer Memberfunktion wie `GetNextToken` abgeleitet werden, die zum Extrahieren und Formatieren von Zeichendaten istream-Member aufrufen kann.

## <a name="see-also"></a>Siehe auch

[Eingabestreams](../standard-library/input-streams.md)<br/>
