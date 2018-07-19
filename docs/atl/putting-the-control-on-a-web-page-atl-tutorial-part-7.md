---
title: Platzieren des Steuerelements auf einer Webseite (ATL-Lernprogramm, Teil 7) | Microsoft Docs
ms.custom: get-started-article
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: conceptual
dev_langs:
- C++
ms.assetid: 50dc4c95-c95b-4006-b88a-9826f7bdb222
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 0cd4076ac34af6ee4b19687f401376265bf0e872
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
ms.locfileid: "32362583"
---
# <a name="putting-the-control-on-a-web-page-atl-tutorial-part-7"></a>Platzieren des Steuerelements auf einer Webseite (ATL-Lernprogramm, Teil 7)
Das Steuerelement ist jetzt fertig. Um zu sehen, wie das Steuerelement in einer realen Situation funktioniert, platzieren Sie es auf einer Webseite. Eine HTML-Datei, die das Steuerelement enthält, wurde erstellt, als Sie das Steuerelement definiert haben. Öffnen Sie die Datei PolyCtl.htm aus **Projektmappen-Explorer**, sehen Sie das Steuerelement auf einer Webseite.  
  
 In diesem Schritt programmieren Sie die Webseite so, dass sie auf Ereignisse reagiert. Außerdem ändern Sie das Steuerelement, um Internet Explorer zu informieren, dass das Steuerelement für die Skripterstellung sicher ist.  
  
## <a name="scripting-the-web-page"></a>Skripterstellung für die Webseite  
 Das Steuerelement ist noch nicht aktiv. Ändern Sie die Website, sodass sie auf die Ereignisse reagiert, die Sie senden.  
  
#### <a name="to-script-the-web-page"></a>Zur Skripterstellung für die Webseite  
  
1.  Öffnen Sie PolyCtl.htm und wählen Sie die HTML-Ansicht aus. Fügen Sie dem HTML-Code die folgenden Zeilen hinzu. Sie sollten nach `</OBJECT>` und vor `</BODY>` hinzugefügt werden.  
  
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
  
2.  Speichern Sie die HTM-Datei.  
  
 Sie haben einigen VBScript-Code hinzugefügt, der die Seiteneigenschaft vom Steuerelement abruft und die Anzahl der Seiten um eins erhöht, wenn Sie innerhalb des Steuerelements klicken. Wenn Sie außerhalb des Steuerelements klicken, reduzieren Sie die Anzahl der Seiten um eine.  
  
## <a name="indicating-that-the-control-is-safe-for-scripting"></a>Angeben, dass das Steuerelement für die Skripterstellung sicher ist  
 Sie können die Webseite mit dem Steuerelement in Internet Explorer anzeigen. Noch benutzerfreundlicher ist es aber, die in Visual C++ integrierte Webbrowseransicht zu verwenden. Um das Steuerelement in der Webbrowseransicht anzuzeigen, mit der rechten Maustaste PolyCtl.htm, und klicken Sie auf **in Browser anzeigen**.  
  
 Auf Grundlage der aktuellen Internet Explorer-Sicherheitseinstellungen erhalten Sie möglicherweise ein Dialogfeld mit einer Sicherheitswarnung, die besagt, dass das Steuerelement möglicherweise nicht sicher für die Skriptausführung ist und möglicherweise Schaden anrichten kann. Wenn Sie beispielsweise ein Steuerelement hätten, das eine Datei anzeigen würde, aber auch eine `Delete`-Methode hätte, die eine Datei löscht, wäre es sicher, wenn es nur auf der Seite angezeigt würde. Es wäre aber nicht sicher für die Skriptausführung, denn jemand könnte die `Delete`-Methode aufrufen.  
  
> [!IMPORTANT]
>  Für dieses Lernprogramm können Sie die Sicherheitseinstellungen in Internet Explorer ändern, um ActiveX-Steuerelemente auszuführen, die nicht als sicher gekennzeichnet sind. Klicken Sie in der Systemsteuerung auf **Interneteigenschaften** , und klicken Sie auf **Sicherheit** so ändern Sie die entsprechenden Einstellungen. Wenn Sie das Lernprogramm abgeschlossen haben, ändern Sie die Sicherheitseinstellungen zurück zu ihrem ursprünglichen Zustand.  
  
 Sie können programmgesteuert Internet Explorer benachrichtigen, dass für dieses spezielle Steuerelement kein Sicherheitswarnungs-Dialogfeld angezeigt werden muss. Hierzu können Sie mit der `IObjectSafety` -Schnittstelle, und die ATL stellt eine Implementierung dieser Schnittstelle in der Klasse [IObjectSafetyImpl](../atl/reference/iobjectsafetyimpl-class.md). Um die Schnittstelle Ihrem Steuerelement hinzuzufügen, fügen Sie `IObjectSafetyImpl` der Liste der geerbten Klassen hinzu, und fügen Sie dafür einen Eintrag in der COM-Zuordnung hinzu.  
  
#### <a name="to-add-iobjectsafetyimpl-to-the-control"></a>So fügen Sie IObjectSafetyImpl dem Steuerelement hinzu  
  
1.  Fügen Sie die folgende Zeile dem Ende der Liste geerbter Klassen in PolyCtl.h hinzu, und fügen Sie der vorherigen Zeile ein Komma hinzu:  
  
 [!code-cpp[NVC_ATL_Windowing#62](../atl/codesnippet/cpp/putting-the-control-on-a-web-page-atl-tutorial-part-7_1.h)]  
  
2.  Fügen Sie die folgende Zeile der COM-Zuordnung in PolyCtl.h hinzu:  
  
 [!code-cpp[NVC_ATL_Windowing#63](../atl/codesnippet/cpp/putting-the-control-on-a-web-page-atl-tutorial-part-7_2.h)]  
  
## <a name="building-and-testing-the-control"></a>Erstellen und Testen des Steuerelements  
 Erstellen Sie das Steuerelement. Sobald der Buildvorgang abgeschlossen ist, öffnen Sie wieder PolyCtl.htm in der Browseransicht. Dieses Mal sollte die Webseite direkt ohne das Sicherheitswarnungs-Dialogfeld angezeigt werden. Klicken Sie innerhalb des Polygons; die Anzahl der Seiten wird um eins erhöht. Klicken Sie außerhalb des Polygons, um die Anzahl der Seiten zu verringern. Wenn Sie versuchen, die Anzahl der Seiten unter drei zu verringern, finden Sie die Fehlermeldung, die Sie festgelegt haben.  
  
 [Zurück zu Schritt 6](../atl/adding-a-property-page-atl-tutorial-part-6.md)  
  
## <a name="next-steps"></a>Nächste Schritte  
 Damit ist das ATL-Lernprogramm beendet. Links zu weiteren Informationen über ATL finden Sie in der [ATL-Startseite](../atl/active-template-library-atl-concepts.md).  
  
## <a name="see-also"></a>Siehe auch  
 [Lernprogramm](../atl/active-template-library-atl-tutorial.md)

