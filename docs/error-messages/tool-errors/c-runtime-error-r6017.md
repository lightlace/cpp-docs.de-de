---
title: C-Laufzeitfehler R6017 | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- R6017
dev_langs:
- C++
helpviewer_keywords:
- R6017
ms.assetid: df3ec5f5-6771-4648-ba06-0e26c6a1cc6a
caps.latest.revision: 7
author: corob-msft
ms.author: corob
manager: ghogen
translation.priority.ht:
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- ru-ru
- zh-cn
- zh-tw
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
ms.translationtype: Machine Translation
ms.sourcegitcommit: 6cad5222fb0d97594d5b13b5cf8903eb2934ee88
ms.openlocfilehash: 903d440dbedbe704ae28be643337619ca1e09c69
ms.contentlocale: de-de
ms.lasthandoff: 02/24/2017

---
# <a name="c-runtime-error-r6017"></a>C-Laufzeitfehler R6017
Unerwarteter multithread-Lock-Fehler  
  
> [!NOTE]
>  Wenn Sie diese Fehlermeldung erhalten, während eine Anwendung ausgeführt wird, wurde die app beendet, da es sich um ein internes Problem enthält. Es gibt mehrere mögliche Ursachen für diesen Fehler, jedoch wird häufig durch einen Fehler in der app-Code verursacht.  
>   
>  Sie können versuchen, diesen Fehler zu beheben, indem Sie folgende Schritte ausführen:  
>   
>  -   Verwenden der **Apps und Features** oder **Programme und Funktionen** Seite der **Systemsteuerung** zu reparieren oder installieren Sie das Programm.  
> -   Überprüfen Sie **Windows Update** in der **Systemsteuerung** für Softwareupdates.  
> -   Überprüfen Sie eine aktualisierte Version der app. Besteht das Problem weiterhin, wenden Sie sich an den app-Hersteller.  
  
 **Informationen für Programmierer**  
  
 Der Prozess empfangen einen unerwarteten Fehler beim Versuch, eine C-Laufzeit multithread-Sperre auf eine Systemressource zugreifen. Dieser Fehler tritt gewöhnlich auf, wenn der Prozess unbeabsichtigt die Laufzeit-Heapdaten ändert. Sie können jedoch auch durch einen internen Fehler in der Common Language runtimebibliothek oder Betriebssystem-Code verursacht werden.  
  
 Um dieses Problem zu beheben, überprüfen Sie die Heap-Beschädigung Fehlern im Code. Weitere Informationen und Beispiele finden Sie unter [CRT-Debuggen Heap Details](/visualstudio/debugger/crt-debug-heap-details). Als Nächstes überprüfen Sie, dass Sie die neuesten verteilbaren Komponenten für Ihre app-Bereitstellung verwenden. Weitere Informationen finden Sie unter [Bereitstellung in Visual C++](../../ide/deployment-in-visual-cpp.md).
