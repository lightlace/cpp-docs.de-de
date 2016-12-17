---
title: "Platzieren des Steuerelements auf einer Webseite (ATL-Lernprogramm, Teil 7)"
ms.custom: na
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "get-started-article"
dev_langs: 
  - "C++"
ms.assetid: 50dc4c95-c95b-4006-b88a-9826f7bdb222
caps.latest.revision: 15
caps.handback.revision: "10"
ms.author: "mblome"
manager: "ghogen"
---
# Platzieren des Steuerelements auf einer Webseite (ATL-Lernprogramm, Teil 7)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Das Steuerelement ist jetzt fertig.  Um zu sehen, wie das Steuerelement in einer realen Situation funktioniert, platzieren Sie es auf einer Webseite.  Eine HTML\-Datei, die das Steuerelement enthält, wurde erstellt, als Sie das Steuerelement definiert haben.  Öffnen Sie die Datei PolyCtl.htm aus dem **Projektmappen\-Explorer**, und Sie können das Steuerelement auf einer Webseite finden.  
  
 In diesem Schritt programmieren Sie die Webseite so, dass sie auf Ereignisse reagiert.  Außerdem ändern Sie das Steuerelement, um Internet Explorer zu informieren, dass das Steuerelement für die Skripterstellung sicher ist.  
  
## Skripterstellung für die Webseite  
 Das Steuerelement ist noch nicht aktiv. Ändern Sie die Website, sodass sie auf die Ereignisse reagiert, die Sie senden.  
  
#### Zur Skripterstellung für die Webseite  
  
1.  Öffnen Sie PolyCtl.htm und wählen Sie die HTML\-Ansicht aus.  Fügen Sie dem HTML\-Code die folgenden Zeilen hinzu.  Sie sollten nach `</OBJECT>` und vor `</BODY>` hinzugefügt werden.  
  
    ```  
  
    <SCRIPT LANGUAGE="VBScript">  
    <!--  
    Sub PolyCtl_ClickIn(x, y)  
       PolyCtl.Sides = PolyCtl.Sides + 1  
    End Sub  
    Sub PolyCtl_ClickOut(x, y)  
       PolyCtl.Sides = PolyCtl.Sides - 1  
    End Sub  
    -->  
    </SCRIPT>  
    ```  
  
2.  Speichern Sie die HTM\-Datei.  
  
 Sie haben einigen VBScript\-Code hinzugefügt, der die Seiteneigenschaft vom Steuerelement abruft und die Anzahl der Seiten um eins erhöht, wenn Sie innerhalb des Steuerelements klicken.  Wenn Sie außerhalb des Steuerelements klicken, reduzieren Sie die Anzahl der Seiten um eine.  
  
## Angeben, dass das Steuerelement für die Skripterstellung sicher ist  
 Sie können die Webseite mit dem Steuerelement in Internet Explorer anzeigen. Noch benutzerfreundlicher ist es aber, die in Visual C\+\+ integrierte Webbrowseransicht zu verwenden.  Um das Steuerelement in der Webbrowseransicht anzuzeigen, klicken Sie mit der rechten Maustaste auf PolyCtl.htm, und klicken Sie dann auf **In Browser anzeigen**.  
  
 Auf Grundlage der aktuellen Internet Explorer\-Sicherheitseinstellungen erhalten Sie möglicherweise ein Dialogfeld mit einer Sicherheitswarnung, die besagt, dass das Steuerelement möglicherweise nicht sicher für die Skriptausführung ist und möglicherweise Schaden anrichten kann.  Wenn Sie beispielsweise ein Steuerelement hätten, das eine Datei anzeigen würde, aber auch eine `Delete`\-Methode hätte, die eine Datei löscht, wäre es sicher, wenn es nur auf der Seite angezeigt würde.  Es wäre aber nicht sicher für die Skriptausführung, denn jemand könnte die `Delete`\-Methode aufrufen.  
  
> [!IMPORTANT]
>  Für dieses Lernprogramm können Sie die Sicherheitseinstellungen in Internet Explorer ändern, um ActiveX\-Steuerelemente auszuführen, die nicht als sicher gekennzeichnet sind.  Klicken Sie in der Systemsteuerung auf **Interneteigenschaften** und dann auf **Sicherheit** , um die entsprechenden Einstellungen zu ändern.  Wenn Sie das Lernprogramm abgeschlossen haben, ändern Sie die Sicherheitseinstellungen zurück zu ihrem ursprünglichen Zustand.  
  
 Sie können programmgesteuert Internet Explorer benachrichtigen, dass für dieses spezielle Steuerelement kein Sicherheitswarnungs\-Dialogfeld angezeigt werden muss.  Dies kann mithilfe der `IObjectSafety`\-Schnittstelle erfolgen, und die ATL stellt eine Implementierung dieser Schnittstelle in der Klasse [IObjectSafetyImpl](../atl/reference/iobjectsafetyimpl-class.md) bereit.  Um die Schnittstelle Ihrem Steuerelement hinzuzufügen, fügen Sie `IObjectSafetyImpl` der Liste der geerbten Klassen hinzu, und fügen Sie dafür einen Eintrag in der COM\-Zuordnung hinzu.  
  
#### So fügen Sie IObjectSafetyImpl dem Steuerelement hinzu  
  
1.  Fügen Sie die folgende Zeile dem Ende der Liste geerbter Klassen in PolyCtl.h hinzu, und fügen Sie der vorherigen Zeile ein Komma hinzu:  
  
     [!CODE [NVC_ATL_Windowing#62](../CodeSnippet/VS_Snippets_Cpp/NVC_ATL_Windowing#62)]  
  
2.  Fügen Sie die folgende Zeile der COM\-Zuordnung in PolyCtl.h hinzu:  
  
     [!CODE [NVC_ATL_Windowing#63](../CodeSnippet/VS_Snippets_Cpp/NVC_ATL_Windowing#63)]  
  
## Erstellen und Testen des Steuerelements  
 Erstellen Sie das Steuerelement.  Sobald der Buildvorgang abgeschlossen ist, öffnen Sie wieder PolyCtl.htm in der Browseransicht.  Dieses Mal sollte die Webseite direkt ohne das Sicherheitswarnungs\-Dialogfeld angezeigt werden.  Klicken Sie innerhalb des Polygons; die Anzahl der Seiten wird um eins erhöht.  Klicken Sie außerhalb des Polygons, um die Anzahl der Seiten zu verringern.  Wenn Sie versuchen, die Anzahl der Seiten unter drei zu verringern, finden Sie die Fehlermeldung, die Sie festgelegt haben.  
  
 [Zurück zu Schritt 6](../atl/adding-a-property-page-atl-tutorial-part-6.md)  
  
## Nächste Schritte  
 Damit ist das ATL\-Lernprogramm beendet.  Links zu weiteren Informationen über ATL finden Sie auf der [ATL\-Startseite](../atl/active-template-library-atl-concepts.md).  
  
## Siehe auch  
 [Lernprogramm](../atl/active-template-library-atl-tutorial.md)