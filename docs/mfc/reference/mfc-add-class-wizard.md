---
title: MFC-Klassen-Assistenten hinzufügen | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- vc.codewiz.class.mfc.simple.overview
dev_langs:
- C++
helpviewer_keywords:
- MFC Add Class Wizard
- wizards [MFC]
ms.assetid: ad3b0989-d307-43b2-9417-3f9a78889024
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 9560dec12a7710076f752d5329269c844f0d3a8b
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33373410"
---
# <a name="mfc-add-class-wizard"></a>MFC-Assistent zum Hinzufügen von Klassen
Verwenden Sie diesen Code-Assistenten aus, um einem vorhandenen MFC-Projekt eine Klasse hinzuzufügen, oder so eine ATL-Projekt eine Klasse hinzu, der MFC unterstützt. Sie können auch MFC-Klassen hinzufügen, die Win32-Projekte, die MFC-Unterstützung verfügen. Funktionen, die Sie beim Erstellen des Projekts angegeben bestimmen, die in diesem Dialogfeld verfügbaren Optionen.  
  
## <a name="names"></a>Namen  
 Geben Sie auf dieser Seite den Klassennamen, Basisklasse und Dateinamen für die neue Klasse.  
  
 **Klassenname**  
 Gibt den Namen der neuen Klasse und bildet die Grundlage für die Standardeinstellung für die Namen von IDs und Dateien auf dieser Seite. C++-Klassen werden in der Regel mit "C", beginnen, z. B. "CMyClass" "MeineKlasse.h", und so weiter.  
  
 **Basisklasse**  
 Gibt den Namen der Basisklasse für die neue Klasse. Standardmäßig ist die Basisklasse [CWnd](../../mfc/reference/cwnd-class.md). Die Basisklasse, die Sie auswählen, bestimmt, ob die anderen Felder auf dieser Seite aktiv sind.  
  
 Der Typ der Klasse, die Sie festlegen, wie die Basisklasse bestimmt, ob die Klasse ein Dialogfeld oder eine Ressourcen-ID verfügt. Die allgemeinen Arten von Klassen lauten folgendermaßen:  
  
-   Klassen wie [CButton](../../mfc/reference/cbutton-class.md), [CWnd](../../mfc/reference/cwnd-class.md), oder [CDocument](../../mfc/reference/cdocument-class.md), die erfordern eines Dialogs oder Ressourcen-ID Diese Klassen verwenden Sie eine Dialogfeld oder Ressourcen-ID nicht Bei Auswahl einer dieser Klassen als Basisklasse der **Dialogfeld ID** Feld und die **DHTML-Ressourcen-ID** Feld sind abgeblendet.  
  
-   Klassen wie [CDialog](../../mfc/reference/cdialog-class.md), [CFormView](../../mfc/reference/cformview-class.md), oder [CPropertyPage](../../mfc/reference/cpropertypage-class.md), die erfordern einer Dialogfeld-ID.  
  
-   Die Klasse [CDHtmlDialog](../../mfc/reference/cdhtmldialog-class.md), wofür eine Dialogfeld-ID, eine DHTML-Ressourcen-ID und den Namen einer HTML-Datei.  
  
 Für Klassen, die eine Dialogfeld-ID erfordern, möglicherweise als effizienter, verwenden Sie die [Ressourcen-Editor](../../windows/resource-editors.md) zum Erstellen der Dialogfeldressource weisen Sie seine ID in der [Fenster "Eigenschaften"](/visualstudio/ide/reference/properties-window), und erstellen Sie eine Klasse, die verknüpft sind mit dieser Ressource-ID. Finden Sie unter [Erstellen eines neuen Dialogfelds](../../windows/creating-a-new-dialog-box.md) für Weitere Informationen zum Erstellen einer Windows-Standarddialogfeld.  
  
> [!NOTE]
>  Wenn Sie eine Dialogfeldressource zuerst erstellen, und leiten Sie die neue Klasse von `CDHtmlDialog`, löschen Sie das Windows-Standarddialogfeld **OK** und **"Abbrechen"** Schaltflächen, die auf das standardmäßige Dialogfeld angezeigt. Das Windows-Standarddialogfeld hostet DHTML-Formular, das einen eigenen enthält **OK** und **"Abbrechen"** Schaltflächen.  
  
 Während das Dialogfeld Windows-Steuerelemente und DHTML-Steuerelemente enthalten kann, wird nicht empfohlen.  
  
 **Dialogfeld-ID**  
 Gibt die ID des Dialogs, wenn Sie ausgewählt haben `CDialog`, `CFormView`, `CPropertyPage`, oder `CDHtmlDialog` als die **Basisklasse**.  
  
 **.h-Datei**  
 Legt den Namen der Headerdatei für die neue Klasse des Objekts. Standardmäßig basiert auf den Namen, die Sie, in angeben diesen Namen **Klassenname**. Klicken Sie auf die Schaltfläche mit den Auslassungspunkten, um den Dateinamen an den Speicherort Ihrer Wahl speichern oder die Klassendeklaration an eine vorhandene Datei anfügen. Wenn Sie eine vorhandene Datei auswählen, der Assistent wird nicht zum Speichern an den ausgewählten Speicherort bis auf **Fertig stellen** im Assistenten.  
  
 Der Assistent überschreibt eine Datei nicht. Wenn Sie den Namen einer vorhandenen Datei auswählen, wenn Sie auf **Fertig stellen**, werden vom Assistenten aufgefordert, um anzugeben, ob die Klassendeklaration an den Inhalt der Datei angefügt werden sollen. Klicken Sie auf **Ja** anzufügende Datei ein, klicken Sie auf **keine** zum Assistenten zurückzukehren, und geben Sie einen anderen Dateinamen an.  
  
 **CPP-Datei**  
 Legt den Namen der Implementierungsdatei für das neue Objekt-Klasse. Standardmäßig basiert auf den Namen, die Sie, in angeben diesen Namen **Klassenname**. Klicken Sie auf die Schaltfläche mit den Auslassungspunkten, um den Dateinamen am Speicherort Ihrer Wahl zu speichern. Die Datei wird nicht an den ausgewählten Speicherort gespeichert, bis Sie auf **Fertig stellen** im Assistenten.  
  
 Der Assistent überschreibt eine Datei nicht. Wenn Sie den Namen einer vorhandenen Datei auswählen, wenn Sie auf **Fertig stellen**, werden vom Assistenten aufgefordert, um anzugeben, ob die Implementierung der Klasse mit dem Inhalt der Datei angefügt werden sollen. Klicken Sie auf **Ja** anzufügende Datei ein, klicken Sie auf **keine** zum Assistenten zurückzukehren, und geben Sie einen anderen Dateinamen an.  
  
 **Active accessibility**  
 MFC Unterstützung für Active Accessibility ermöglicht, durch den Aufruf [EnableActiveAccessibility](../../mfc/reference/cwnd-class.md#enableactiveaccessibility) im Konstruktor. Diese Option ist verfügbar, für die abgeleitete Klassen [CWnd](../../mfc/reference/cwnd-class.md).  
  
 **DHTML-Ressourcen-ID**  
 Bezieht sich auf von abgeleiteten Klassen `CDHtmlDialog` nur. Gibt die Ressourcen-ID des DHTML-Dialogfelds an. Die Ressourcen-ID wird im HTML-Abschnitt der RC-Datei des Projekts zusammen mit der Datei den Namen des HTML-Dialogfeld angezeigt. Klicken Sie im Dialogfeld DHTML-Ressource, die durch diese ID identifizierte gehostet wird, identifiziert durch **Dialogfeld ID**.  
  
 **. HTML-Datei.**  
 Bezieht sich auf von abgeleiteten Klassen `CDHtmlDialog` nur. Legt den Namen der HTML-Datei für das DHTML-Dialogfeld. Der Dateiname basiert standardmäßig auf den Klassennamen abrufen. Der Dateiname wird im HTML-Abschnitt der RC-Datei des Projekts zusammen mit den DHTML Dialogfeld klicken Sie im Ressourcen-ID angezeigt.  
  
 **Automatisierung**  
 Legt die Klasse Maß an Unterstützung für [Automatisierung](../../mfc/automation.md). Automatisierung auf Klassenebene ist für alle Klassen, die Unterstützung der Automatisierung verfügbar. Es steht auch für Projekte mit Unterstützung für die Automatisierung erstellt. Also entweder eine MFC Projekt an, [ATL unterstützt](../../atl/reference/mfc-support-in-atl-projects.md), oder einem MFC-Projekt für die Auswahl der **Automatisierung** Kontrollkästchen in der [erweiterte Funktionen](../../mfc/reference/advanced-features-mfc-application-wizard.md) auf der Seite die MFC-Bibliothek Anwendungs-Assistent.  
  
|Option|Beschreibung|  
|------------|-----------------|  
|**Keine**|Gibt an, dass die Klasse keine Automation-Unterstützung verfügt.|  
|**Automatisierung**|Gibt an, dass die Klasse die Automatisierung unterstützt. Wenn Sie diese Option auswählen, ist die neu erstellte Klasse als programmierbares Objekt von Automation-Clientanwendungen, z. B. Microsoft Visual Basic und Microsoft Excel verfügbar. Diese Option ist nicht verfügbar für die Basisklassen, die nach dieser Tabelle aufgeführt.|  
|**Erstellbar nach Typ-ID**|Gibt an, dass die Klasse und die Projekt unterstützen andere Anwendungen, die Objekte dieser Klasse mithilfe von Automatisierung erstellen. Mit dieser Option können Automatisierungsclients ein Automatisierungsobjekt direkt erstellen. Die Typ-ID im Textfeld wird von der Clientanwendung verwendet, zum Angeben des Objekts erstellt werden. Es wird die systemweite und muss eindeutig sein. Diese Option ist nicht verfügbar für die Basisklassen, die nach dieser Tabelle aufgeführt.|  
  
 -Unterstützung ist nicht für den folgenden Basisklassen verfügbar:  
  
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
 Legt die Typ-ID der Klasse fest. Die **Typ-ID** Feld verkettet den Projektnamen und den Klassennamen der neuen wie folgt: *MFCProj.MFCClass*. Diese ID ist Objekteigenschaft nur bei Auswahl der **Automatisierung** Option **anhand von Typ-ID erstellbar**.  
  
 **Erstellte DocTemplate-Ressourcen**  
 Gibt an, dass der von der Anwendung erstellten Dokumente besitzen Dokument Vorlagenressourcen verfügen. Um dieses Kontrollkästchen aktivieren, muss das Projekt die MFC-Dokument-/ Ansichtarchitektur unterstützen, und die Basisklasse dieser Klasse muss [CFormView](../../mfc/reference/cformview-class.md).  
  
 Finden Sie unter [Dokumentvorlagen und der Erstellungsvorgang für die Dokument-/Ansichtarchitektur](../../mfc/document-templates-and-the-document-view-creation-process.md) für Weitere Informationen.  
  
## <a name="see-also"></a>Siehe auch  
 [MFC-Klasse](../../mfc/reference/adding-an-mfc-class.md)   
 [Hinzufügen einer Klasse](../../ide/adding-a-class-visual-cpp.md)
