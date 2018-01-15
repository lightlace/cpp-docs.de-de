---
title: "Ratschläge für allgemeine MBCS-Programmierung | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: _mbcs
dev_langs: C++
helpviewer_keywords:
- MBCS [C++], dialog box fonts
- MS Shell Dlg
- MBCS [C++], programming
- dialog boxes [C++], fonts
ms.assetid: 7b541235-f3e5-4af0-b2c2-a0112cd5fbfb
caps.latest.revision: "9"
author: ghogen
ms.author: ghogen
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 8a09bfb9b30e279e8d0b7696055c1e54ac56bfae
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="general-mbcs-programming-advice"></a>Allgemeine Ratschläge für die MBCS-Programmierung
Verwenden Sie die folgenden Tipps:  
  
-   Verwenden Sie Flexibilität erhalten Sie, wie z. B. Makros zur Laufzeit `_tcschr` und `_tcscpy` nach Möglichkeit. Weitere Informationen finden Sie unter [Zuordnungen für generischen Text in Tchar.h](../text/generic-text-mappings-in-tchar-h.md).  
  
-   Verwenden Sie die C-Laufzeit `_getmbcp` Funktion zum Abrufen von Informationen über die aktuelle Codepage.  
  
-   Zeichenfolgenressourcen nicht wiederverwendet werden. Abhängig von der Zielsprache möglicherweise eine bestimmte Zeichenfolge eine andere Bedeutung, wenn übersetzt. Hauptmenü "File" auf der Anwendungsverzeichnis könnte z. B. unterschiedlich aus der Zeichenfolge "File" in einem Dialogfeld übersetzen. Wenn Sie mehr als eine Zeichenfolge mit dem gleichen Namen verwenden möchten, verwenden Sie für jede verschiedenen Zeichenfolgen-IDs.  
  
-   Möglicherweise möchten herausfinden, ob Ihre Anwendung unter einem MBCS-fähigen Betriebssystem ausgeführt wird. Zu diesem Zweck legen Sie ein Flag beim Programmstart; verlassen Sie sich nicht auf API-Aufrufe.  
  
-   Beim Entwerfen von Dialogfeldern können Sie ca. 30 % zusätzliche Leerzeichen am Ende des statischen Text-Steuerelemente für die MBCS-Übersetzung.  
  
-   Gehen Sie beim Auswählen von Schriftarten für Ihre Anwendung sein, da einige Schriftarten nicht auf allen Systemen verfügbar sind. Die japanische Version von Windows 2000 unterstützt beispielsweise nicht die Schriftart Helvetica.  
  
-   Verwenden Sie bei der Auswahl der Schriftart für Dialogfelder [MS Shell Dlg](http://msdn.microsoft.com/library/windows/desktop/dd374112) anstelle von MS Sans Serif oder Helvetica. MS Shell Dlg wird durch die richtige Schriftart vom System vor dem Erstellen des Dialogfelds "" ersetzt. Die Verwendung von MS Shell Dlg wird sichergestellt, dass alle Änderungen im Betriebssystem für den Umgang mit dieser Schriftart automatisch zur Verfügung stehen. (MFC ersetzt MS Shell Dlg durch DEFAULT_GUI_FONT oder Systemschriftart unter Windows 95, Windows 98 und Windows NT 4, da diese Systeme MS Shell Dlg nicht ordnungsgemäß behandeln.)  
  
-   Beim Entwerfen Ihrer Anwendung entscheiden Sie, welche Zeichenfolgen lokalisiert werden können. Im Zweifelsfall wird davon ausgegangen Sie, dass alle angegebene Zeichenfolge lokalisiert werden. Kombinieren Sie Zeichenfolgen, die lokalisiert werden können daher nicht mit denen, die nicht.  
  
## <a name="see-also"></a>Siehe auch  
 [Tipps für die MBCS-Programmierung](../text/mbcs-programming-tips.md)   
 [Inkrementieren und Dekrementieren von Zeigern](../text/incrementing-and-decrementing-pointers.md)