---
title: "Allgemeine Ratschl&#228;ge f&#252;r die MBCS-Programmierung"
ms.custom: na
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "article"
f1_keywords: 
  - "_mbcs"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Dialogfelder [C++], Schriftarten"
  - "MBCS [C++], Dialogfeldschriftarten"
  - "MBCS [C++], Programmieren"
  - "MS Shell Dlg"
ms.assetid: 7b541235-f3e5-4af0-b2c2-a0112cd5fbfb
caps.latest.revision: 9
caps.handback.revision: "9"
ms.author: "ghogen"
manager: "ghogen"
---
# Allgemeine Ratschl&#228;ge f&#252;r die MBCS-Programmierung
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Beachten Sie folgende Tipps:  
  
-   Verwenden Sie aus Flexibilitätsgründen nach Möglichkeit Laufzeitmakros wie `_tcschr` und `_tcscpy`.  Weitere Informationen finden Sie unter [Zuordnungen für generischen Text in Tchar.h](../text/generic-text-mappings-in-tchar-h.md).  
  
-   Verwenden Sie die C\-Laufzeitfunktion `_getmbcp`, um Informationen über die aktuelle Codepage abzufragen.  
  
-   Verwenden Sie Zeichenfolgenressourcen nur einmal.  Abhängig von der Zielsprache kann eine Zeichenfolge nach der Übersetzung unterschiedliche Bedeutungen haben.  Das Wort "Datei" wird z. B. im Hauptmenü der Anwendung häufig anders übersetzt als die entsprechende Zeichenfolge in einem Dialogfeld.  Wenn Sie gleichlautende Zeichenfolgen verwenden müssen, versehen Sie jede Zeichenfolge mit einer anderen Zeichenfolgen\-ID.  
  
-   In bestimmten Fällen müssen Sie herausfinden, ob eine Anwendung unter einem MBCS\-aktivierten Betriebssystem ausgeführt wird.  Legen Sie zu diesem Zweck ein entsprechendes Flag beim Programmstart fest. API\-Aufrufe sind in dieser Hinsicht unzuverlässig.  
  
-   Halten Sie beim Entwurf von Dialogfeldern in statischen Textsteuerelementen etwa ein Drittel zusätzlichen Platz frei, um die MBCS\-Übersetzung zu ermöglichen.  
  
-   Gehen Sie bei der Schriftartenauswahl für eine Anwendung überlegt vor, da bestimmte Schriftarten nicht auf jedem System verfügbar sind.  Die japanische Version von Windows 2000 unterstützt z. B. die Schriftart Helvetica nicht.  
  
-   Verwenden Sie als Schriftart für Dialogfelder statt MS Sans Serif oder Helvetica [MS Shell Dlg](http://msdn.microsoft.com/library/windows/desktop/dd374112).  MS Shell Dlg wird vor Erstellung des Dialogfelds vom System gegen die korrekte Schriftart ausgetauscht.  Mit MS Shell Dlg können Sie sicherstellen, dass sämtliche Änderungen im Betriebssystem, die sich auf diese Schriftart beziehen, automatisch zur Verfügung gestellt werden. \(MFC ersetzt MS Shell Dlg mit DEFAULT\_GUI\_FONT oder der Systemschrift unter Windows 95, Windows 98 und Windows NT 4, da diese Systeme MS Shell Dlg nicht ordnungsgemäß behandeln.\)  
  
-   Legen Sie beim Entwurf einer Anwendung fest, welche Zeichenfolgen lokalisiert werden können.  Gehen Sie im Zweifelsfall davon aus, dass eine Zeichenfolge lokalisiert wird.  Kombinieren Sie daher auf keinen Fall lokalisierbare und nicht lokalisierbare Zeichenfolgen.  
  
## Siehe auch  
 [Tipps für die MBCS\-Programmierung](../text/mbcs-programming-tips.md)   
 [Inkrementieren und Dekrementieren von Zeigern](../text/incrementing-and-decrementing-pointers.md)