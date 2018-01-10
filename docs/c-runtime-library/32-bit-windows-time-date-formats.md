---
title: 32-Bit-Windows-Uhrzeit-/Datumsformate | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: vc.time
dev_langs: C++
helpviewer_keywords: 32-bit Windows
ms.assetid: ef1589db-84d7-4b24-8799-7c7a22cfe2bf
caps.latest.revision: "6"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 20e812a1eca6e620e0c1847b6ea6a07b871a407d
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="32-bit-windows-timedate-formats"></a>32-Bit-Windows-Uhrzeit-/Datumsformate
Die Zeit- und Datumsangaben der Datei werden mithilfe von ganzen Zahlen ohne Vorzeichen als Bitfelder einzeln gespeichert. Zeit- und Datumsangaben der Datei werden folgendermaßen gepackt:  
  
### <a name="time"></a>zeit  
  
|Bitposition:|0   1   2   3   4|5 6 7 8 9 A|B C D E F|  
|-------------------|-----------------------|---------------------------|-----------------------|  
|Länge:|5|6|5|  
|Inhalte:|Stunden|Minuten|Zweisekündiges Inkrement|  
|Wertebereich:|0-23|0-59|0-29 in zweisekündigen Abständen|  
  
### <a name="date"></a>Datum  
  
|Bitposition:|0   1   2   3   4   5   6|7 8 9 A|B C D E F|  
|-------------------|-------------------------------|-------------------|-----------------------|  
|Länge:|7|4|5|  
|Inhalte:|Jahr|Monat|Tag|  
|Wertebereich:|0-119|1-12|1-31|  
||(relativ zu 1980)|||  
  
## <a name="see-also"></a>Siehe auch  
 [Globale Konstanten](../c-runtime-library/global-constants.md)