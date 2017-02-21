---
title: "Adding or Deleting a String | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vc.editors.string"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "strings [C++], adding to string tables"
  - "string tables, deleting strings"
  - "strings [C++], deleting in string tables"
  - "string tables, adding strings"
ms.assetid: 077077b4-0f4b-4633-92d6-60b321164cab
caps.latest.revision: 11
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 8
---
# Adding or Deleting a String
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Mit dem Zeichenfolgen\-Editor können Sie schnell neue Einträge in die Zeichenfolgentabelle einfügen.  Neue Zeichenfolgen werden am Ende der Tabelle eingefügt; sie erhalten den nächsten freien Bezeichner.  Die Eigenschaften **ID**, **Wert** oder **Beschriftung** können ggf. im [Eigenschaftenfenster](../Topic/Properties%20Window.md) bearbeitet werden.  
  
 Durch den Zeichenfolgen\-Editor wird sichergestellt, dass Sie keine bereits vergebene ID verwenden.  Wenn Sie eine ID auswählen, die bereits in Gebrauch ist, gibt der Zeichenfolgen\-Editor eine entsprechende Meldung aus und weist eine generische eindeutige ID zu, z. B. **IDS\_STRING58113**.  
  
### So fügen Sie einer Zeichenfolgentabelle einen Eintrag hinzu  
  
1.  Öffnen Sie die Zeichenfolgentabelle, indem Sie in der [Ressourcenansicht](../windows/resource-view-window.md) auf das zugehörige Symbol doppelklicken.  
  
    > [!NOTE]
    >  Wenn das Projekt noch keine RC\-Datei enthält, informieren Sie sich unter [Erstellen einer neuen Ressourcenskriptdatei](../windows/how-to-create-a-resource-script-file.md).  
  
2.  Klicken Sie mit der rechten Maustaste auf die Zeichenfolgentabelle, und wählen Sie im Kontextmenü die Option **Neue Zeichenfolge** aus.  
  
3.  Wählen Sie im **Zeichenfolgen**\-Editor aus der Dropdownliste eine **ID** aus, oder geben Sie eine ID direkt ein.  
  
4.  Bearbeiten Sie, falls erforderlich, den Eintrag unter **Wert**.  
  
5.  Geben Sie einen Eintrag für **Beschriftung** ein.  
  
    > [!NOTE]
    >  NULL\-Zeichenfolgen sind in Windows\-Zeichenfolgentabellen nicht zulässig.  Wenn Sie in der Zeichenfolgentabelle einen Eintrag erstellen, der eine NULL\-Zeichenfolge ist, erhalten Sie die Meldung "Geben Sie eine Zeichenfolge für diesen Tabelleneintrag ein".  
  
### So löschen Sie einen Eintrag aus einer Zeichenfolgentabelle  
  
1.  Wählen Sie den zu löschenden Eintrag aus.  
  
2.  Klicken Sie im Menü **Bearbeiten** auf **Löschen**.  
  
 \- oder \-  
  
-   Klicken Sie mit der rechten Maustaste auf die zu löschende Zeichenfolge, und wählen Sie im Kontextmenü den Befehl **Löschen**.  
  
 \- oder \-  
  
-   Drücken Sie die ENTF\-TASTE.  
  
 Informationen zum Hinzufügen von Ressourcen zu verwalteten Projekten \(die die Common Language Runtime zum Ziel haben\) finden Sie unter [Ressourcen in Anwendungen](../Topic/Resources%20in%20Desktop%20Apps.md) im *.NET Framework\-Entwicklerhandbuch.* Informationen zum manuellen Hinzufügen von Ressourcendateien zu verwalteten Projekten, zum Zugreifen auf Ressourcen, zum Anzeigen statischer Ressourcen und zum Zuweisen von Ressourcenzeichenfolgen zu Eigenschaften finden Sie unter [Exemplarische Vorgehensweise: Lokalisieren von Windows Forms](assetId:///9a96220d-a19b-4de0-9f48-01e5d82679e5) und [Walkthrough: Using Resources for Localization with ASP.NET](../Topic/Walkthrough:%20Using%20Resources%20for%20Localization%20with%20ASP.NET.md).  
  
 **Anforderungen**  
  
 Win32  
  
## Siehe auch  
 [String Editor](../mfc/string-editor.md)   
 [Zeichenfolgen](_win32_Strings)   
 [Informationen zu Zeichenfolgen](_win32_About_Strings_cpp)