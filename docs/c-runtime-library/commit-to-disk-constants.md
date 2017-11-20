---
title: Commit-To-Disk-Konstanten | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: vc.constants
dev_langs: C++
helpviewer_keywords: commit-to-disk constants
ms.assetid: 0b903b23-b4fa-431e-a937-51d95f695ecf
caps.latest.revision: "6"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 128b670302683208680fbf1499c26af474c72c3e
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/24/2017
---
# <a name="commit-to-disk-constants"></a>Commit-To-Disk-Konstanten
**Microsoft-spezifisch**  
  
## <a name="syntax"></a>Syntax  
  
```  
  
#include <stdio.h>  
```  
  
## <a name="remarks"></a>Hinweise  
 Diese Microsoft-spezifischen Konstanten geben an, ob der mit der geöffneten Datei verknüpfte Puffer in Betriebssystempuffer oder auf Datenträger geleert wird. Der Modus ist in der Zeichenfolge enthalten, die den Typ des Lese-/Schreibzugriffs angibt (**"r"**, **"w"**, **"a"**, **"r+"**, **"w+"**, **"a+"**).  
  
 Folgende Datenträgercommitmodi sind vorhanden:  
  
 **c**  
 Schreibt nicht geschriebene Inhalte des angegebenen Puffers auf den Datenträger. Diese Datenträgercommitfunktionalität erfolgt nur bei expliziten Aufrufen der Funktionen [fflush](../c-runtime-library/reference/fflush.md) oder [_flushall](../c-runtime-library/reference/flushall.md). Dieser Modus ist für den Umgang mit sensiblen Daten nützlich. Wenn Sie Ihr Programm beispielsweise nach einem Aufruf von `fflush` oder `_flushall` beenden, können Sie sicherstellen, dass Ihre Daten zu den Betriebssystempuffern gelangt sind. Wird eine Datei jedoch mit der Option **c** geöffnet, gelangen die Daten möglicherweise niemals zum Datenträger, wenn das Betriebssystem ebenfalls beendet wird.  
  
 **n**  
 Schreibt nicht geschriebene Inhalte des angegebenen Puffers in die Betriebssystempuffer. Das Betriebssystem kann Daten zwischenspeichern und dann einen optimalen Zeitpunkt ermitteln, um Daten auf den Datenträger zu schreiben. In vielen Situationen kann dieses Verhalten ein effizientes Programmverhalten bewirken. Wenn die Aufbewahrung von Daten (z.B. Banktransaktionen oder Informationen zu Flugtickets) allerdings von entscheidender Bedeutung ist, sollten Sie eventuell die Option **c** verwenden. Die Standardeinstellung ist der **n**-Modus.  
  
> [!NOTE]
>  Die Optionen **c** und **n** sind nicht Teil des ANSI-Standards für `fopen`, stellen jedoch Microsoft-Erweiterungen dar und sollten nicht verwendet werden, wenn ANSI-Portabilität gewünscht ist.  
  
## <a name="using-the-commit-to-disk-feature-with-existing-code"></a>Verwenden der Datenträgercommitfunktion mit vorhandenem Code  
 Standardmäßig schreiben Aufrufe der Bibliotheksfunktionen [fflush](../c-runtime-library/reference/fflush.md) oder [_flushall](../c-runtime-library/reference/flushall.md) Daten in die vom Betriebssystem verwalteten Puffer. Das Betriebssystem ermittelt die optimale Zeit, um die Daten tatsächlich auf den Datenträger zu schreiben. Mit der Datenträgercommitfunktion der Laufzeitbibliothek können Sie sicherstellen, dass wichtige Daten direkt auf den Datenträger anstatt in die Betriebssystempuffer geschrieben werden. Sie können diese Funktion einem vorhandenen Programm ermöglichen, ohne es umschreiben zu müssen, indem Sie die Objektdateien mit COMMODE.OBJ verknüpfen.  
  
 In der resultierenden ausführbaren Datei werden die Inhalte des Puffers durch Aufrufe von `fflush` direkt auf den Datenträger geschrieben, während die Inhalte aller Puffer durch Aufrufe von `_flushall` auf den Datenträger geschrieben werden. Dies sind die einzigen beiden von COMMODE.OBJ betroffenen Funktionen.  
  
 **Ende Microsoft-spezifisch**  
  
## <a name="see-also"></a>Siehe auch  
 [Stream-E/A](../c-runtime-library/stream-i-o.md)   
 [_fdopen, _wfdopen](../c-runtime-library/reference/fdopen-wfdopen.md)   
 [fopen, _wfopen](../c-runtime-library/reference/fopen-wfopen.md)   
 [Globale Konstanten](../c-runtime-library/global-constants.md)