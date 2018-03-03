---
title: "Vorteile und Nachteile der Methode zum Verknüpfen mit der CRT verwendet | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- _ATL_MIN_CRT macro
ms.assetid: 49b485f7-9487-49e4-b12a-0f710b620e2b
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 244415a947918a836e8c4c67dbd18758ec40393c
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
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

