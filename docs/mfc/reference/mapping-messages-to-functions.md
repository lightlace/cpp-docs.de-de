---
title: "Zuordnen von Meldungen zu Funktionen"
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
  - "vc.codewiz.mapping.msg.function"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Meldungszuordnungen [C++], Zuordnen von Meldungen zu Funktionen"
  - "Windows-Nachrichten [C++], Hinzufügen von Meldungshandlern"
ms.assetid: a7727a62-f638-4b20-b7f5-131f47200d6a
caps.latest.revision: 9
caps.handback.revision: "5"
ms.author: "mblome"
manager: "ghogen"
---
# Zuordnen von Meldungen zu Funktionen
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Im Eigenschaftenfenster können Sie Meldungshandler \(Memberfunktionen von MFC\-Benutzeroberflächenklassen\) an die Meldungen binden, die durch die Anwendungsressourcen generiert wurden.  Sie verwenden [MFC\-Meldungszuordnungen](../../mfc/messages-and-commands-in-the-framework.md), um die Bindung herzustellen.  
  
 Wenn Sie in der Klassenansicht eine neue Klasse erstellen, die von einer der Framework\-Klassen abgeleitet ist, wird automatisch eine vollständige und funktionale Klasse in die angegebene Headerdatei \(**.h**\) und die Implementierungsdatei \(**.cpp**\) eingefügt.  
  
> [!NOTE]
>  Um eine neue Klasse hinzuzufügen, die keine Meldungen verarbeitet, erstellen Sie die Klasse direkt im Text\-Editor.  
  
### So definieren oder entfernen Sie einen Meldungshandler im Eigenschaftenfenster  
  
1.  Klicken Sie in der Klassenansicht auf die Klasse.  
  
2.  Klicken Sie im Eigenschaftenfenster auf die Schaltfläche **Meldungen**.  
  
    > [!NOTE]
    >  Die Schaltfläche **Meldungen** ist verfügbar, wenn Sie entweder den Klassennamen in der Klassenansicht markieren oder wenn Sie auf eine beliebige Stelle im Quellcodefenster klicken.  
  
     Wenn das Projekt über einen Handler für eine Meldung verfügt, wird der Name des Handlers in der rechten Spalte neben der Meldung angezeigt.  
  
3.  Wenn die Meldung kein Handler verfügt, klicken Sie auf die Zelle in der rechten Spalte des Eigenschaftenfensters, um den vorgeschlagenen Namen des Handlers als \<addHandlerName\>anzuzeigen. \(Beispielweise, schlägt \<der Meldungshandler `WM_TIMER` hinzufügen \>`OnTimer` vor.\)  
  
4.  Klicken Sie auf den vorgeschlagenen Namen, um der Funktion Stubcode hinzuzufügen.  
  
5.  Um einen Meldungshandler zu bearbeiten, doppelklicken Sie in der Klassenansicht auf die Meldung und bearbeiten den Code im Quellcodefenster.  
  
 Um einen Meldungshandler zu entfernen, doppelklicken Sie in der rechten Spalte auf den Handler und wählen Sie \<deleteHandlerName\>aus.  Der Funktionscode wird auskommentiert.  
  
## Siehe auch  
 [MFC\-Meldungshandler](../../mfc/reference/adding-an-mfc-message-handler.md)   
 [Hinzufügen neuer Funktionen mit Code\-Assistenten](../../ide/adding-functionality-with-code-wizards-cpp.md)   
 [Hinzufügen einer Klasse](../../ide/adding-a-class-visual-cpp.md)   
 [Hinzufügen einer Memberfunktion](../../ide/adding-a-member-function-visual-cpp.md)   
 [Hinzufügen einer Membervariablen](../../ide/adding-a-member-variable-visual-cpp.md)   
 [Überschreiben einer virtuellen Funktion](../../ide/overriding-a-virtual-function-visual-cpp.md)   
 [Adding Event Handlers for Dialog Box Controls](../../mfc/adding-event-handlers-for-dialog-box-controls.md)   
 [Navigieren in der Klassenstruktur](../../ide/navigating-the-class-structure-visual-cpp.md)