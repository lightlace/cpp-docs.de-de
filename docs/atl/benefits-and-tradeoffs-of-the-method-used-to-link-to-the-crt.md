---
title: Vorteile und Nachteile der Methode zum Verknüpfen mit der CRT verwendet | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- _ATL_MIN_CRT macro
ms.assetid: 49b485f7-9487-49e4-b12a-0f710b620e2b
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: b2835e88da11b8d8332226080eb860afd41c0702
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
---
# <a name="benefits-and-tradeoffs-of-the-method-used-to-link-to-the-crt"></a>Vorteile und Nachteile der Methode zum Verknüpfen mit der CRT verwendet
Das Projekt kann statisch oder dynamisch mit der CRT verknüpfen. In der folgenden Tabelle werden die vor- und Nachteile bei der Auswahl der zu verwendenden Methode.  
  
|Methode|Vorteil|Kompromiss|  
|------------|-------------|--------------|  
|Das statische Verknüpfen mit der CRT<br /><br /> (**-Laufzeitbibliothek** festgelegt **Singlethread-**)|Die CRT-DLL muss nicht auf dem System, in dem das Abbild ausgeführt wird.|Das Abbild erheblich erhöhen die Größe ca. 25 KB Startcode hinzugefügt.|  
|Dynamisches Verknüpfen mit der CRT<br /><br /> (**-Laufzeitbibliothek** festgelegt **Multithreaded**)|Das Bild erfordert keine den CRT-Startcode, daher ist es wesentlich kleiner.|Die CRT-DLL muss auf dem System, das Abbild ausgeführt werden.|  
  
 Das Thema [Verknüpfen mit der CRT in ATL-Projekt](../atl/linking-to-the-crt-in-your-atl-project.md) erläutert, wie auf die Art und Weise, in, das mit der CRT verknüpft.  
  
## <a name="see-also"></a>Siehe auch  
 [Programmieren mit ATL- und C-Laufzeitcode](../atl/programming-with-atl-and-c-run-time-code.md)   
 [DLLs und Verhalten von Visual C++-Laufzeitbibliothek](../build/run-time-library-behavior.md)   
 [CRT-Bibliotheksfunktionen](../c-runtime-library/crt-library-features.md)

