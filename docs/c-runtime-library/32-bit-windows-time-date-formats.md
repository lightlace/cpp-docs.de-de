---
title: 32-Bit-Windows-Uhrzeit-/Datumsformate | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- vc.time
dev_langs:
- C++
helpviewer_keywords:
- 32-bit Windows
ms.assetid: ef1589db-84d7-4b24-8799-7c7a22cfe2bf
caps.latest.revision: 6
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
translationtype: Human Translation
ms.sourcegitcommit: 3f91eafaf3b5d5c1b8f96b010206d699f666e224
ms.openlocfilehash: bd00adddbf728aae66120fede63e0b6a0c5439a7
ms.lasthandoff: 04/01/2017

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
