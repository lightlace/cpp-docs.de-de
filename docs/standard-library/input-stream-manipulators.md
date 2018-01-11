---
title: Eingabestream-Manipulatoren | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- input streams, manipulators
- input stream objects
ms.assetid: 0addcacb-7b7b-4d70-9775-a59abc400fb3
caps.latest.revision: "8"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 17242528dd2be4a72a763f34ee651fc170fea58c
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="input-stream-manipulators"></a>Eingabestream-Manipulatoren
Viele Manipulatoren, z.B. [setprecision]--brokenlink--(../Topic/not%20found:3ddde610-70cc-4cfa-8a89-3e83d1d356a8.md#setprecision), werden für die `ios`-Klasse definiert und somit für Eingabestreams verwendet. Einige Manipulatoren beeinflussen jedoch tatsächlich Eingabestreamobjekte. Für diejenigen, die das tun, sind die Basismanipulatoren `dec`, `oct` und `hex` die Wichtigsten, welche die Konvertierungsbasis festlegen, die Zahlen aus dem Eingabestream verwendet.  
  
 Während des Extrahierens ermöglicht der `hex`-Manipulator die Verarbeitung von verschiedenen Eingabeformaten. Zum Beispiel c, C, 0xc, 0xC, 0Xc und 0XC werden alle als die ganze Dezimalzahl 12 interpretiert. Jedes Zeichen außer 0 bis 9, A bis F, a bis f, x und X beendet die numerische Konvertierung. Demnach wird die Sequenz `"124n5"` mit dem festgelegten [basic_ios::fail](../standard-library/basic-ios-class.md#fail)-Bit in die Zahl 124 konvertiert.  
  
## <a name="see-also"></a>Siehe auch  
 [Eingabestreams](../standard-library/input-streams.md)

