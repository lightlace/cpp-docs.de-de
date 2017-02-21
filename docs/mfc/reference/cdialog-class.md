---
title: "CDialog Class | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "CDialog"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CDialog class"
  - "MFC-Dialogfelder, Basisklasse"
  - "Modale Dialogfelder, Erstellen"
  - "Nicht modale Dialogfelder, Erstellen"
  - "Nicht modale Dialogfelder, Anzeigen"
ms.assetid: ca64b77e-2cd2-47e3-8eff-c2645ad578f9
caps.latest.revision: 23
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 24
---
# CDialog Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Die Basisklasse verwendet zum Anzeigen von Dialogfeldern auf dem Bildschirm.  
  
## Syntax  
  
```  
class CDialog : public CWnd  
```  
  
## Mitglieder  
  
### Öffentliche Konstruktoren  
  
|Name|Description|  
|----------|-----------------|  
|[CDialog::CDialog](../Topic/CDialog::CDialog.md)|Erstellt ein `CDialog`\-Objekt.|  
  
### Öffentliche Methoden  
  
|Name|Description|  
|----------|-----------------|  
|[CDialog::Create](../Topic/CDialog::Create.md)|Initialisiert das `CDialog`\-Objekt.  Stellt ein nicht modales Dialogfeld erstellt und fügt es dem `CDialog`\-Objekt.|  
|[CDialog::CreateIndirect](../Topic/CDialog::CreateIndirect.md)|Stellt ein nicht modales Dialogfeld aus einer Dialogfeldvorlage im Arbeitsspeicher erstellt \(nicht ressourcenbasiert\).|  
|[CDialog::DoModal](../Topic/CDialog::DoModal.md)|Ruft ein modales Dialogfeld auf und gibt zurück, wenn die.|  
|[CDialog::EndDialog](../Topic/CDialog::EndDialog.md)|Schließt ein modales Dialogfeld.|  
|[CDialog::GetDefID](../Topic/CDialog::GetDefID.md)|Ruft die ID des standardmäßigen Pushbutton\-Steuerelements für ein Dialogfeld.|  
|[CDialog::GotoDlgCtrl](../Topic/CDialog::GotoDlgCtrl.md)|Verschiebt den Fokus auf ein angegebenes Dialogfeld\-Steuerelement im Dialogfeld.|  
|[CDialog::InitModalIndirect](../Topic/CDialog::InitModalIndirect.md)|Stellt ein modales Dialogfeld aus einer Dialogfeldvorlage im Arbeitsspeicher erstellt \(nicht ressourcenbasiert\).  Die Parameter werden gespeichert, bis die Funktion `DoModal` aufgerufen wurde.|  
|[CDialog::MapDialogRect](../Topic/CDialog::MapDialogRect.md)|Konvertiert die Dialogeinheiten eines Rechtecks, um Einheiten zu stößt.|  
|[CDialog::NextDlgCtrl](../Topic/CDialog::NextDlgCtrl.md)|Verschiebt den Fokus auf das nächste Dialogfeld\-Steuerelement im Dialogfeld.|  
|[CDialog::OnInitDialog](../Topic/CDialog::OnInitDialog.md)|Überschreiben Sie, um von Dialogfeldinitialisierung zu erweitern.|  
|[CDialog::OnSetFont](../Topic/CDialog::OnSetFont.md)|Überschreiben Sie, um die Schriftarten anzugeben, dass ein Dialogfeld\-Steuerelement, zu verwenden ist, beim Zeichnen von Text.|  
|[CDialog::PrevDlgCtrl](../Topic/CDialog::PrevDlgCtrl.md)|Verschiebt den Fokus auf das vorherige Dialogfeld\-Steuerelement im Dialogfeld.|  
|[CDialog::SetDefID](../Topic/CDialog::SetDefID.md)|Ändert das standardmäßige Pushbutton\-Steuerelement für ein Dialogfeld mit einem angegebenen Pushbutton.|  
|[CDialog::SetHelpID](../Topic/CDialog::SetHelpID.md)|Legt eine ID der kontextbezogenen Hilfe für das Dialogfeld fest.|  
  
### Geschützte Methoden  
  
|Name|Description|  
|----------|-----------------|  
|[CDialog::OnCancel](../Topic/CDialog::OnCancel.md)|Überschreiben Sie, um die Schaltfläche Abbrechen oder der ESC\-TASTEen\-Aktion auszuführen.  Standardmäßig wird das Dialogfeld und die **DoModal**  gibt **IDCANCEL**.|  
|[CDialog::OnOK](../Topic/CDialog::OnOK.md)|Überschreiben Sie, um die Aktion auf OK in einem modalen Dialogfeld auszuführen.  Standardmäßig wird das Dialogfeld und die `DoModal` gibt **IDOK**.|  
  
## Hinweise  
 Dialogfelder gibt zwei Typen von Mutexen: modale und nicht modale.  Ein modales Dialogfeld muss vom Benutzer geschlossen werden, bevor die Anwendung weiterhin.  Ein nicht modales Dialogfeld ermöglicht dem Benutzer, um das Dialogfeld anzuzeigen und zu einer anderen Aufgabe zurückzukehren, ohne das Dialogfeld abzubrechen oder zu entfernen.  
  
 Ein Objekt `CDialog` ist eine Dialogfeldvorlage und des `CDialog` von abgeleitete Klasse.  Verwenden Sie den Dialog\-Editor, um die Dialogfeldvorlage zu erstellen und in einer Ressource zu speichern, verwenden Sie den Hinzufügens\-Klassenassistenten, um eine Klasse erstellen, die von `CDialog` abgeleitet wird.  
  
 Ein Dialogfeld, wie jedes andere Fenster, empfängt Nachrichten von Windows.  In einem Dialogfeld können Sie an den Behandlungsbenachrichtigungsmeldungen von den Steuerelementen des Dialogfelds seit dem besonders relevant, das ist, wie der Benutzer auf das Dialogfeld interagiert.  Verwenden Sie das Eigenschaftenfenster, um auszuwählen, welche Meldungen Sie behandeln möchten und es die entsprechenden Meldungszuordnungseinträge und die Meldungshandlermemberfunktionen der Klasse selbst eingefügt.  Sie müssen nur anwendungsspezifischen Code in den Handlermemberfunktionen schreiben.  
  
 Wenn Sie es vorziehen, können Sie Meldungszuordnungseinträge und Memberfunktionen immer manuell schreiben.  
  
 Mit trivialsten im Dialogfeld fügen Sie Membervariablen der abgeleiteten Dialogfeldklasse zum Speichern von Daten hinzu, die in die Steuerelemente des Dialogfelds vom Benutzer eingegebenen Daten oder für den Benutzer.  Sie können den Assistenten zum Hinzufügen von Variablen verwenden, um Membervariablen erstellen und mit Steuerelementen zuzuordnen.  Gleichzeitig wählen Sie einen Variablentyp und einen zulässigen Wertebereich für jede Variable aus.  Der Code\-Assistent fügt die Membervariablen der abgeleiteten Dialogfeldklasse hinzu.  
  
 Eine Datenumsetzung wird generiert, um den Austausch von Daten zwischen den Membervariablen und den Steuerelementen des Dialogfelds automatisch zu behandeln.  Die Datenumsetzung bietet Funktionen, die die Steuerelemente im Dialogfeld mit den richtigen Werten initialisieren, die Daten abrufen und die Daten überprüfen.  
  
 Um ein modales Dialogfeld zu erstellen, erstellen Sie ein Objekt auf dem Stapel mithilfe des Konstruktors für die abgeleitete Dialogfeldklasse und rufen Sie dann auf `DoModal` um das Dialogfeld und ihre Steuerelemente zu erstellen.  Wenn Sie ein nicht modales Dialogfeld erstellen möchten, rufen Sie **Create** im Konstruktor der Dialogfeldklasse auf.  
  
 Sie können eine Vorlage im Arbeitsspeicher auch erstellen, indem Sie eine [DLGTEMPLATE](http://msdn.microsoft.com/library/windows/desktop/ms645394) Datenstruktur verwenden, wie in [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)] beschrieben.  Nachdem Sie ein `CDialog`\-Objekt erstellen, rufen Sie [CreateIndirect](../Topic/CDialog::CreateIndirect.md) auf, um ein nicht modales Dialogfeld oder Aufruf [InitModalIndirect](../Topic/CDialog::InitModalIndirect.md) und [DoModal](../Topic/CDialog::DoModal.md) erstellen, um ein modales Dialogfeld zu erstellen.  
  
 Die Austausch\- und ValidierungsDatenumsetzung wird in eine Überschreibung von `CWnd::DoDataExchange` geschrieben, die der neuen Dialogfeldklasse hinzugefügt wird.  Siehe die [DoDataExchange](../Topic/CWnd::DoDataExchange.md)\-Memberfunktion in `CWnd` für mehr auf der Austausch\- und Validierungsfunktionalität.  
  
 rufen der Programmierer und Framework `DoDataExchange` indirekt durch einen Aufruf [CWnd::UpdateData](../Topic/CWnd::UpdateData.md) auf.  
  
 Das Framework ruft `UpdateData` auf, wenn der Benutzer auf die Schaltfläche "OK" klickt, um ein modales Dialogfeld zu schließen.  \(Die Daten werden nicht abgerufen, wenn auf die Schaltfläche Abbrechen geklickt wird\). Die Standardimplementierung von [OnInitDialog](../Topic/CDialog::OnInitDialog.md) ruft auch `UpdateData` auf, um die Anfangswerte der Steuerelemente festlegen.  Sie überschreiben in der Regel `OnInitDialog`, um Steuerelemente weiter zu initialisieren.  `OnInitDialog` wird schließlich die Dialogfeld\-Steuerelemente aufgerufen werden erstellt und vor dem Dialogfeld wird angezeigt.  
  
 Sie können `CWnd::UpdateData` während der Ausführung von einem modalen oder von einem nicht modalen Dialogfeld jederzeit aufrufen.  
  
 Wenn Sie ein Dialogfeld manuell entwickeln, fügen Sie die erforderlichen Membervariablen der abgeleiteten Dialogfeldklasse sich hinzu, und Sie fügen Memberfunktionen hinzu, um diese Werte festzulegen oder abzurufen.  
  
 Ein modales Dialogfeld schließt automatisch, wenn der Benutzer die OK oder Abbrechen klickt, oder wenn der Code die `EndDialog`\-Memberfunktion aufruft.  
  
 Wenn Sie ein nicht modales Dialogfeld, immer überschreiben Sie die `OnCancel`\-Memberfunktion und rufen Sie `DestroyWindow` aus ihr auf.  Rufen Sie nicht die Basisklasse `CDialog::OnCancel` auf, da sie `EndDialog` aufruft, die das Dialogfeld nicht sichtbar erstellt, jedoch nicht beschädigt wird.  Sie sollten `PostNcDestroy` für nicht modale Dialogfelder auch überschreiben, um **this** zu löschen, da nicht modale Dialogfelder normalerweise mit **new** zugeordnet werden.  Modale Dialogfelder werden normalerweise auf den Frame erstellt und nicht `PostNcDestroy` Bereinigung erfordern.  
  
 Weitere Informationen zu `CDialog`, finden Sie unter:  
  
-   [Dialogfelder](../../mfc/dialog-boxes.md)  
  
-   Knowledge Base\-Artikel Q262954: HOWTO: Erstellen Sie ein Resizeable\-Dialogfeld mit Bildlaufleisten erstellt  
  
## Vererbungshierarchie  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 `CDialog`  
  
## Anforderungen  
 **Header:** afxwin.h  
  
## Siehe auch  
 [MFC überprüft DLGCBR32](../../top/visual-cpp-samples.md)   
 [MFC\-Beispiel DLGTEMPL](../../top/visual-cpp-samples.md)   
 [CWnd\-Klasse](../../mfc/reference/cwnd-class.md)   
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)