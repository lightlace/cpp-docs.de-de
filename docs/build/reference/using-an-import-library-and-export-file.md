---
title: Verwenden einer Importbibliothek und einer Exportdatei | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-tools
ms.tgt_pltfrm: ''
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- circular exports
- import libraries, using
- export files
ms.assetid: 2634256a-8aa5-4495-8c9e-6cde10e4ed76
caps.latest.revision: 7
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 37d77fdc4df7d2e7239b8bba652d8cf8f4bbc997
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="using-an-import-library-and-export-file"></a>Verwenden einer Importbibliothek und einer Exportdatei
Wenn ein Programm (eine ausführbare Datei oder eine DLL-Datei) exportiert, in ein anderes Programm, dem es auch importiert, oder, wenn mehr als zwei Programme zu exportieren und von einander importieren, müssen die Befehle zum Verknüpfen dieser Programme zirkuläre Exporte berücksichtigen.  
  
 Wenn aus einem anderen Programm verknüpfen ein Programm, verwendet exportiert werden, müssen Sie in einer Situation ohne zirkuläre Exporte die Importbibliothek für das ausführende Programm angeben. Die Importbibliothek für das ausführende Programm wird erstellt, wenn Sie das ausführende Programm verknüpfen. Aus diesem Grund müssen Sie das ausführende Programm vor dem Import von Programm verknüpfen. Z. B. wenn TWO.dll aus ONE.dll importiert werden kann, müssen Sie zuerst ONE.dll verknüpfen und die Importbibliothek ONE.lib abrufen. Dann geben Sie beim Verknüpfen von TWO.dll ONE.lib. Wenn der Linker TWO.dll erstellt, wird auch die Importbibliothek TWO.lib erstellt. Verwenden Sie TWO.lib beim Verknüpfen von Programmen, die aus TWO.dll importieren.  
  
 In einer Exportsituation zirkulären ist es jedoch nicht möglich, alle voneinander abhängigen Programme mit Importbibliotheken andere Programme zu verknüpfen. Im Beispiel, wenn TWO.dll exportiert ebenfalls um ONE.dll, die Importbibliothek für TWO.dll nicht vorhanden. noch nicht beim ONE.dll verknüpft ist. Wenn zirkuläre Exporte vorhanden sind, müssen Sie LIB zum Erstellen einer Importbibliothek und eine Exportdatei für eines der Programme verwenden.  
  
 Um zu beginnen, wählen Sie eines der Programme auf dem LIB ausgeführt. Klicken Sie in der LIB-Befehl sind alle Objekte und Bibliotheken für das Programm, und geben Sie/DEF an Wenn das Programm eine DEF-Datei oder/Export-Spezifikationen verwendet, geben Sie diese ebenfalls.  
  
 Nach der Erstellung der Importbibliothek (.lib) und die Exportdatei (.exp) für die Anwendung verwenden Sie beim Verknüpfen von anderen Programm oder Programme der Importbibliothek her. LINK erstellt eine Importbibliothek für jedes ausführende Programm, das sie erstellt. Wenn das Ausführen von LIB für die Objekte und Exporte für ONE.dll erstellen Sie z. B. ONE.lib und ONE.exp. Sie können jetzt ONE.lib verwenden, beim Verknüpfen von TWO.dll. Dieser Schritt wird auch die Importbibliothek TWO.lib erstellt.  
  
 Verknüpfen Sie schließlich das Programm, dem Sie mit begonnen wurde. Geben Sie in der LINK-Befehl die Objekte und Bibliotheken für das Programm mit der .exp-Datei, die LIB für das Programm und die Importbibliothek erstellt oder Bibliotheken für die vom Programm verwendeten Exporte. Zum Fortsetzen des Vorgangs im Beispiels enthält die LINK-Befehl für ONE.dll ONE.exp und TWO.lib sowie die Objekte und Bibliotheken, die in One.dll enthalten sind. Geben Sie die DEF-Datei oder/Export-Spezifikationen nicht in die LINK-Befehl; Diese sind nicht erforderlich, da die Exportdefinitionen in der .exp-Datei enthalten sind. Wenn Sie die Verwendung einer .exp-Datei verknüpfen, wird LINK erstellt eine Importbibliothek nicht, da vorausgesetzt wird, dass eine wurde erstellt, wenn die .exp-Datei erstellt wurde.  
  
## <a name="see-also"></a>Siehe auch  
 [Arbeiten mit Importbibliotheken und Exportdateien](../../build/reference/working-with-import-libraries-and-export-files.md)