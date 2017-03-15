---
title: "MFC-Klassen-Assistenten hinzufügen | Microsoft-Dokumentation"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- vc.codewiz.class.mfc.simple.overview
dev_langs:
- C++
helpviewer_keywords:
- MFC Add Class Wizard
- wizards [MFC]
ms.assetid: ad3b0989-d307-43b2-9417-3f9a78889024
caps.latest.revision: 16
author: mikeblome
ms.author: mblome
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
translationtype: Machine Translation
ms.sourcegitcommit: 4fafe461008e3545243d693e0d9e34acd57163e0
ms.openlocfilehash: 08d258c2b8386a4dd0c1d24c6ac6aa10f6c04a63
ms.lasthandoff: 02/24/2017

---
# <a name="mfc-add-class-wizard"></a>MFC-Assistent zum Hinzufügen von Klassen
Mit diesem Code-Assistenten können Sie einem vorhandenen MFC-Projekt eine Klasse hinzuzufügen, oder um ein ATL-Projekt eine Klasse hinzuzufügen, die MFC unterstützt. Sie können auch MFC-Klassen hinzufügen, die Win32-Projekten, die MFC-Unterstützung verfügen. Funktionen, die Sie beim Erstellen des Projekts angegeben bestimmen, welche Optionen in diesem Dialogfeld.  
  
## <a name="names"></a>Namen  
 Geben Sie auf dieser Seite den Klassennamen, die Basisklasse und die Dateinamen für die neue Klasse.  
  
 **Klassenname**  
 Gibt den Namen der neuen Klasse, und gibt die Standardbasis für die Namen von IDs und Dateien auf dieser Seite. C++-Klassen beginnen normalerweise mit "C", also z. B. "CMyClass" "MeineKlasse.h", und so weiter.  
  
 **Basisklasse**  
 Gibt den Namen der Basisklasse für die neue Klasse. Standardmäßig ist die Basisklasse [CWnd](../../mfc/reference/cwnd-class.md). Die Basisklasse, die Sie auswählen, bestimmt, ob die anderen Felder auf dieser Seite aktiv sind.  
  
 Der Typ der Klasse, die Sie festlegen, wie die Basisklasse bestimmt, ob die Klasse eine Dialogfeld-ID oder eine Ressourcen-ID verfügt. Die allgemeinen Arten von Klassen lauten wie folgt:  
  
-   Klassen wie [CButton](../../mfc/reference/cbutton-class.md), [CWnd](../../mfc/reference/cwnd-class.md), oder [CDocument](../../mfc/reference/cdocument-class.md), die erfordern ein Dialogfeld oder Ressourcen-ID Diese Klassen verwenden Sie eine Dialogfeld oder Ressourcen-ID nicht Wenn Sie eine dieser Klassen als Basisklasse auswählen die **Dialogfeld-ID** Feld und die **DHTML-Ressourcen-ID** Feld sind abgeblendet.  
  
-   Klassen wie [CDialog](../../mfc/reference/cdialog-class.md), [CFormView](../../mfc/reference/cformview-class.md), oder [CPropertyPage](../../mfc/reference/cpropertypage-class.md), die eine Dialogfeld-ID erfordern  
  
-   Die Klasse [CDHtmlDialog](../../mfc/reference/cdhtmldialog-class.md), erfordert eine Dialogfeld-ID, eine DHTML-Ressourcen-ID und den Namen einer HTML-Datei.  
  
 Für Klassen, die eine Dialogfeld-ID erfordern, unter Umständen effizienter, verwenden die [Ressourcen-Editor](../../windows/resource-editors.md) um die Ressource zu erstellen, weisen Sie in die ID der [Eigenschaftenfenster](/visualstudio/ide/reference/properties-window), und erstellen Sie eine Klasse, die Ressourcen-ID zugeordnet Finden Sie unter [Erstellen eines neuen Dialogfelds](../../windows/creating-a-new-dialog-box.md) für Weitere Informationen zum Erstellen einer Windows-Standarddialogfeld.  
  
> [!NOTE]
>  Wenn Sie zuerst eine Dialogressource erstellen und leiten Sie die neue Klasse von `CDHtmlDialog`, löschen Sie die Windows **OK** und **Abbrechen** Schaltflächen, die auf das Dialogfeld angezeigt werden. Das Windows-Standarddialogfeld hostet das DHTML-Formular, das eine eigene enthält **OK** und **Abbrechen** Schaltflächen.  
  
 Während das Dialogfeld Windows-Steuerelemente und DHTML-Steuerelemente enthalten kann, wird nicht empfohlen.  
  
 **Dialogfeld-ID**  
 Gibt die ID des Dialogfelds an, wenn Sie ausgewählt `CDialog`, `CFormView`, `CPropertyPage`, oder `CDHtmlDialog` als die **Basisklasse**.  
  
 **.h-Datei**  
 Legt den Namen der Headerdatei für die neue Klasse des Objekts. Dieser Name basiert standardmäßig auf den Namen, den Sie in **Klassenname**. Klicken Sie auf die Schaltfläche, um den Dateinamen am Speicherort Ihrer Wahl speichern oder die Klassendeklaration an eine vorhandene Datei anfügen. Wenn Sie eine vorhandene Datei auswählen, der Assistent wird gespeichert, am ausgewählten Speicherort bis auf **Fertig stellen** im Assistenten.  
  
 Der Assistent überschrieben eine Datei nicht. Wenn Sie den Namen einer vorhandenen Datei, auswählen, wenn Sie auf **Fertig stellen**, die vom Assistenten aufgefordert, anzugeben, ob die Klassendeklaration an den Inhalt der Datei angefügt werden sollen. Klicken Sie auf **Ja** anzufügenden Datei ein, klicken Sie auf **keine** zum Assistenten zurückzukehren und einen anderen Dateinamen angeben.  
  
 **CPP-Datei**  
 Legt den Namen der Implementierungsdatei für die neue Klasse des Objekts. Dieser Name basiert standardmäßig auf den Namen, den Sie in **Klassenname**. Klicken Sie auf die Schaltfläche mit den Auslassungspunkten, um den Dateinamen am Speicherort Ihrer Wahl zu speichern. Die Datei wird nicht am ausgewählten Speicherort gespeichert, bis Sie auf **Fertig stellen** im Assistenten.  
  
 Der Assistent überschrieben eine Datei nicht. Wenn Sie den Namen einer vorhandenen Datei, auswählen, wenn Sie auf **Fertig stellen**, die vom Assistenten aufgefordert, anzugeben, ob die Implementierung der Klasse an den Inhalt der Datei angefügt werden sollen. Klicken Sie auf **Ja** anzufügenden Datei ein, klicken Sie auf **keine** zum Assistenten zurückzukehren und einen anderen Dateinamen angeben.  
  
 **Active accessibility**  
 MFC Unterstützung für Active Accessibility ermöglicht, durch Aufrufen von [EnableActiveAccessibility](../../mfc/reference/cwnd-class.md#enableactiveaccessibility) im Konstruktor. Diese Option ist verfügbar für Klassen abgeleitete [CWnd](../../mfc/reference/cwnd-class.md).  
  
 **DHTML-Ressourcen-ID**  
 Bezieht sich auf von abgeleiteten Klassen `CDHtmlDialog` nur. Gibt die Ressourcen-ID des DHTML-Dialogfelds. Die Ressourcen-ID wird im HTML-Abschnitt der RC-Datei des Projekts zusammen mit der HTML-Datei im Feld Name angezeigt. Durch diese ID identifizierte DHTML-Ressource befindet sich im Dialogfeld identifizierten **Dialogfeld-ID**.  
  
 **. HTM-Datei**  
 Bezieht sich auf von abgeleiteten Klassen `CDHtmlDialog` nur. Legt den Namen der HTML-Datei für die DHTML-Dialogfeld. Dieser Dateiname basiert standardmäßig auf dem Klassennamen. Der Dateiname wird im HTML-Abschnitt der RC-Datei des Projekts zusammen mit der DHTML Dialogfeld im Feld die Ressourcen-ID angezeigt.  
  
 **Automatisierung**  
 Legt auf Klassenebene der Unterstützung für [Automatisierung](../../mfc/automation.md). Automatisierung auf Klassenebene ist für alle Klassen, die Unterstützung der Automatisierung verfügbar. Es ist auch für mit Unterstützung für Automatisierung erstellte Projekte verfügbar. Also entweder eine MFC Projekt an, [ATL unterstützt](../../atl/reference/mfc-support-in-atl-projects.md), oder einem MFC-Projekt für die Auswahl der **Automatisierung** das Kontrollkästchen der [erweiterte Funktionen](../../mfc/reference/advanced-features-mfc-application-wizard.md) Seite des Assistenten für MFC-Anwendung.  
  
|Option|Beschreibung|  
|------------|-----------------|  
|**Keine**|Gibt an, dass die Klasse keine Automatisierung unterstützt.|  
|**Automatisierung**|Gibt an, dass die Klasse die Automatisierung unterstützt. Wenn Sie diese Option auswählen, ist die neu erstellte Klasse als programmierbares Objekt von Automation-Clientanwendungen, z. B. Microsoft Visual Basic und Microsoft Excel verfügbar. Diese Option ist nicht verfügbar für die Basisklassen, die nach dieser Tabelle aufgeführt.|  
|**Erstellbar nach Typ-ID**|Gibt an, dass die Klasse und das Projekt andere Programme erstellen von Objekten dieser Klasse mit Automation unterstützen. Mit dieser Option können Automatisierungsclients ein Automatisierungsobjekt direkt erstellen. Die Typ-ID im Textfeld wird von der Clientanwendung verwendet, zum Angeben des Objekts erstellt werden. Es gilt systemweit und muss eindeutig sein. Diese Option ist nicht verfügbar für die Basisklassen, die nach dieser Tabelle aufgeführt.|  
  
 Benutzeroberflächenautomatisierungs-Unterstützung ist nicht verfügbar für die folgenden Klassen:  
  
-   `CAsyncMonitorFile`  
  
-   `CAsyncSocket`  
  
-   `CCachedDataPathProperty`  
  
-   `CConnectionPoint`  
  
-   `CDatabase`  
  
-   `CDataPathProperty`  
  
-   `CHttpFilter`  
  
-   `CHttpServer`  
  
-   `CInternetSession`  
  
-   `CObject`  
  
-   `CSocket`  
  
 **Typ-ID**  
 Legt die Typ-ID der Klasse fest. Die **-Typ-ID** Feld werden der Projektname und der neue Klassenname wie folgt verkettet: *MFCProj.MFCClass*. Diese ID kann geändert werden, nur bei Auswahl der **Automatisierung** Option **anhand von Typ-ID erstellbar**.  
  
 **Erstellte DocTemplate-Ressourcen**  
 Gibt an, dass die Dokumente, die von der Anwendung erstellten Ressourcen für Dokumentvorlagen. Um dieses Kontrollkästchen zu aktivieren, muss das Projekt die MFC-Dokument-/ Ansichtarchitektur unterstützen, und die Basisklasse dieser Klasse muss [CFormView](../../mfc/reference/cformview-class.md).  
  
 Finden Sie unter [Dokumentvorlagen und der Erstellungsvorgang für Dokument und Ansicht](../../mfc/document-templates-and-the-document-view-creation-process.md) Weitere Informationen.  
  
## <a name="see-also"></a>Siehe auch  
 [MFC-Klasse](../../mfc/reference/adding-an-mfc-class.md)   
 [Hinzufügen einer Klasse](../../ide/adding-a-class-visual-cpp.md)

