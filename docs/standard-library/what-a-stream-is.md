---
title: Funktionsweise eines Streams | Microsoft-Dokumentation
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
- reading data [C++], iostream programming
- data [C++], reading
- streams [C++], in iostream classes
- streams [C++]
ms.assetid: a7e661e9-6cd1-4543-a9a4-c58ee9fd32f3
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 7515c587a651b31bce7f3d1c56777a2a908c488a
ms.sourcegitcommit: d51ed21ab2b434535f5c1d553b22e432073e1478
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/23/2018
---
# <a name="what-a-stream-is"></a>Funktionsweise eines Streams
Wie C verfügt auch C++ über keine integrierte Eingabe/Ausgabe-Funktion. Alle C++-Compiler werden jedoch zusammen mit einem systematischen, objektorientierten E/A-Paket ausgegeben, bekannt als iostream-Klassen. Der Stream ist das zentrale Konzept der iostream-Klassen. Sie können sich ein Streamobjekt als intelligente Datei vorstellen, die als Quelle und Ziel für Bytes dient. Die Merkmale eines Streams werden durch dessen Klasse und durch benutzerdefinierte Operatoren zum Einfügung und Extrahieren bestimmt.  
  
 Das Betriebssystem des Datenträgers befasst sich über Gerätetreiber mit den Tastatur-, Bildschirm-, Drucker- und Kommunikationsports als erweiterte Dateien. Die iostream-Klassen interagieren mit diesen erweiterten Dateien. Integrierte Klassen unterstützen das Lesen und Schreiben vom und im Arbeitsspeicher mit Syntax, die identisch mit der Syntax für die Datenträger-E/A ist, wodurch es einfach ist, Streamklassen abzuleiten.  
  
## <a name="in-this-section"></a>In diesem Abschnitt  
 [Eingabe-/Ausgabealternativen](../standard-library/input-output-alternatives.md)  
  
## <a name="see-also"></a>Siehe auch  
 [iostream-Programmierung](../standard-library/iostream-programming.md)

