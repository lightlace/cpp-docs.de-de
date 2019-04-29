---
title: Verwenden von Extraktionsoperatoren
ms.date: 11/04/2016
helpviewer_keywords:
- extraction operators [C++]
- '&gt;&gt; operator [C++], extraction operators'
- operators [C++], extraction
ms.assetid: a961e1a9-4897-41de-b210-89d5b2d051ae
ms.openlocfilehash: 1fc6ffd2f033dfe3df60260f734d93b79d6824f0
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62362425"
---
# <a name="using-extraction-operators"></a>Verwenden von Extraktionsoperatoren

Mit dem für alle C++-Standarddatentypen vorprogrammierten Extraktionsoperator (`>>`) können Bytes am einfachsten aus einem Eingabestreamobjekt abgerufen werden.

Bei Extraktionsoperatoren für die Eingabe von formatiertem Text werden eingehende Datenwerte mit Leerzeichen voneinander getrennt. Das ist ungünstig, wenn ein Textfeld mehrere Wörter enthält oder wenn Zahlen durch Kommas voneinander getrennt werden. In solch einem Fall kann die Memberfunktion [istream::getline](../standard-library/basic-istream-class.md#getline) für nicht formatierte Eingabe zum Lesen eines Textblocks mit Leerzeichen verwendet und anschließend der Textblock mit speziellen Funktionen analysiert werden. Alternativ kann auch eine Eingabestreamklasse mit einer Memberfunktion wie `GetNextToken` abgeleitet werden, die zum Extrahieren und Formatieren von Zeichendaten istream-Member aufrufen kann.

## <a name="see-also"></a>Siehe auch

[Eingabestreams](../standard-library/input-streams.md)<br/>
