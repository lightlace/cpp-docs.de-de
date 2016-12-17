---
title: "Example: Implementing a Property Page"
ms.custom: na
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Eigenschaftenseiten, Implementieren"
ms.assetid: c30b67fe-ce08-4249-ae29-f3060fa8d61e
caps.latest.revision: 14
caps.handback.revision: "9"
ms.author: "mblome"
manager: "ghogen"
---
# Example: Implementing a Property Page
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Dieses Beispiel zeigt, wie eine Eigenschaftenseite erstellt, die \(ermöglicht die Änderung\) Eigenschaften der [Dokumentklassen](../mfc/document-classes.md)\-Schnittstelle anzeigt.  Diese Schnittstelle wird von Dokumente in [Beispiele für das Objektmodell der allgemeinen Umgebung](../Topic/Common%20Environment%20Object%20Model%20Examples.md) von Visual Studio verfügbar gemacht \(obwohl die Eigenschaftenseite, die Sie erstellen, nicht wissen, wo die Objekte es stammen von bearbeitet, solange sie die richtige Schnittstelle unterstützen\).  
  
 Das Beispiel basiert auf [ATLPages\-Beispiel](../top/visual-cpp-samples.md).  
  
 Um dieses Beispiel zu vervollständigen, werden Sie:  
  
-   [Fügen Sie die ATL\-Eigenschaftenseitenklasse hinzu](#vcconusing_the_atl_object_wizard) mithilfe des Hinzufügens\-Klassendialogfelds und des ATL\-Eigenschaftenseiten\-Assistenten.  
  
-   [Bearbeiten Sie die Dialogfeldressource](#vcconediting_the_dialog_resource) durch Hinzufügen von neuen Steuerelementen für die interessanten Eigenschaften der **Document**\-Schnittstelle.  
  
-   [Fügen Sie Meldungshandler hinzu](#vcconadding_message_handlers), um die Eigenschaftenseitensite laufend über die vorgenommenen Änderungen vom Benutzer.  
  
-   Fügen Sie mehrere `#import`\-Anweisungen und Typedef im [Haushaltung](#vcconhousekeeping)\-Abschnitt hinzu.  
  
-   [Überschreiben Sie IPropertyPageImpl::SetObjects](#vcconoverriding_ipropertypageimpl_setobjects), um die Objekte, die für die Eigenschaftenseite sicherzustellen übergeben werden.  
  
-   [Überschreiben IPropertyPageImpl::Activate](#vcconoverriding_ipropertypageimpl_activate), um die Schnittstelle der Eigenschaftenseite zu initialisieren.  
  
-   [Überschreiben IPropertyPageImpl::Apply](#vcconoverride_ipropertypageimpl_apply), um des Objekts mit den neuesten Eigenschaftswerten zu aktualisieren.  
  
-   [Zeigen Sie die Eigenschaftenseite an](#vccontesting_the_property_page) durch das Erstellen eines einfachen Hilfeobjekts.  
  
-   [Erstellen Sie ein Makro](#vcconcreating_a_macro), das die Eigenschaftenseite testet.  
  
##  <a name="vcconusing_the_atl_object_wizard"></a> Hinzufügen der ATL\-Eigenschaftenseiten\-Klasse  
 Zunächst erstellen Sie ein neues ATL\-Projekt für einen DLL\-Server, der `ATLPages7` aufgerufen wird.  Verwenden Sie jetzt [ATL\-Eigenschaftenseiten\-Assistent](../atl/reference/atl-property-page-wizard.md), um eine Eigenschaftenseite zu generieren.  Geben Sie, der Eigenschaftenseite **Kurzname** von **DocProperties** fahren Sie zu **Zeichenfolgen** die Seite, um Eigenschaft\-Seitebesondere Elemente wie in der Tabelle unten dargestellt festzulegen.  
  
|Element|Wert|  
|-------------|----------|  
|Titel|TextDocument|  
|Doc Zeichenfolgen\-.|Eigenschaften VCUE TextDocument|  
|werden|*\<blank\>*|  
  
 Die Werte, die Sie festgelegt auf dieser Seite des Assistenten zum Eigenschaftenseitencontainer zurückgegeben werden, wenn sie **IPropertyPage::GetPageInfo** aufruft.  Was in Zeichenfolgen nach geschieht, das vom Container, aber abhängig ist, in der Regel werden sie verwendet, um die Seite an den Benutzer zu identifizieren.  Der Name wird normalerweise in einer Registerkarte zu der Seite und die Doc. Zeichenfolgen\- wird in einer Statusleiste oder in einer QuickInfo angezeigt werden \(wenn auch der Standardeigenschaftenrahmen nicht diese Zeichenfolge vorhanden verwendet\).  
  
> [!NOTE]
>  Die Zeichenfolgen, dass Sie hier festgelegt wie Zeichenfolgenressourcen im Projekt vom Assistenten gespeichert werden.  Sie können diese Zeichenfolgen mithilfe des Ressourcen\-Editor bequem bearbeiten, wenn Sie diese Informationen ändern, nachdem der Code für die Seite generiert wurde.  
  
 **OK** auf das Erstellen des Assistenten die Eigenschaftenseite generieren.  
  
##  <a name="vcconediting_the_dialog_resource"></a> Bearbeiten der Dialogfeldressource  
 Nachdem die Eigenschaftenseite generiert wurde, müssen Sie mehrere Steuerelemente der Dialogfeldressource hinzufügen, die die Seite darstellt.  Fügen Sie ein Eingabefeld, ein Steuerelement Statischer Text und ein Kontrollkästchen hinzu und legen Sie deren IDs wie unten dargestellt fest:  
  
 ![Dialogfeldressource bearbeiten](../atl/media/ppgresourcelabeled.png "PPGResourceLabeled")  
  
 Diese Steuerelemente werden verwendet, um den Dateinamen des Dokuments und des schreibgeschützten Status anzuzeigen.  
  
> [!NOTE]
>  Die Dialogressource enthält nicht Rahmens oder Befehlsschaltflächen, noch verfügt sie die Darstellung im Registerkartenformat, den Sie möglicherweise erwartet.  Diese Funktionen werden von Eigenschaftenseitenframen wie dem bereitgestellt, das mit [OleCreatePropertyFrame](http://msdn.microsoft.com/library/windows/desktop/ms678437) erstellt wird, aufgerufen.  
  
##  <a name="vcconadding_message_handlers"></a> Hinzufügen von Meldungshandlern  
 Mit den Steuerelemente erstellt haben, können Sie Meldungshandler hinzufügen, um den geänderten Status der Seite zu aktualisieren, wenn der Wert aus einer der Kontrollenänderungen:  
  
 [!CODE [NVC_ATL_Windowing#73](../CodeSnippet/VS_Snippets_Cpp/NVC_ATL_Windowing#73)]  
  
 Dieser Code reagiert auf die Änderungen, die am Bearbeitungssteuerelement oder am Kontrollkästchen, indem er [IPropertyPageImpl::SetDirty](../Topic/IPropertyPageImpl::SetDirty.md) vorgenommen werden aufruft, der die Seitensite informiert, dass die Seite geändert hat.  In der Regel reagiert die Seitensite, indem eine **Übernehmen** Schaltfläche auf den Eigenschaftenseitenframen aktiviert oder deaktiviert.  
  
> [!NOTE]
>  In Ihren eigenen Eigenschaftenseiten müssen Sie möglicherweise genau verfolgen, das Eigenschaften vom Benutzer geändert wurden, sodass Sie Eigenschaften zu aktualisieren, vermeiden können, die nicht geändert wurden.  implementiert dieses Beispiels, die Code, indem die ursprünglichen Eigenschaftswerte verfolgen und mit den aktuellen Werten des Benutzeroberfläche vergleichen, wenn es Zeit ist, die Änderungen zu übernehmen.  
  
##  <a name="vcconhousekeeping"></a> Haushaltung  
 Fügen Sie nun ein paar `#import`\-Anweisungen DocProperties.h hinzu, damit der Compiler in der **Document**\-Schnittstelle bemerkt:  
  
 [!CODE [NVC_ATL_Windowing#74](../CodeSnippet/VS_Snippets_Cpp/NVC_ATL_Windowing#74)]  
  
 Sie müssen auch die `IPropertyPageImpl` Basisklasse verweisen; Fügen Sie folgenden `typedef` der **CDocProperties**\-Klasse hinzu:  
  
 [!CODE [NVC_ATL_Windowing#75](../CodeSnippet/VS_Snippets_Cpp/NVC_ATL_Windowing#75)]  
  
##  <a name="vcconoverriding_ipropertypageimpl_setobjects"></a> Überschreiben von IPropertyPageImpl::SetObjects  
 Die erste `IPropertyPageImpl`\-Methode, die Sie überschreiben müssen, ist [SetObjects](../Topic/IPropertyPageImpl::SetObjects.md).  Hier fügen Sie Code hinzu, um zu überprüfen, dass nur ein einzelnes Objekt übergeben wurde und dass die **Document**\-Schnittstelle unterstützt, die Sie erwarten:  
  
 [!CODE [NVC_ATL_Windowing#76](../CodeSnippet/VS_Snippets_Cpp/NVC_ATL_Windowing#76)]  
  
> [!NOTE]
>  Sie ist sinnvoll, nur ein einzelnes Objekt für diese Seite zu unterstützen, da Sie dem Benutzer ermöglichen, den Dateinamen des Objekts festzulegen \- nur eine Datei kann an jedem an einem Speicherort vorhanden sein.  
  
##  <a name="vcconoverriding_ipropertypageimpl_activate"></a> Überschreiben von IPropertyPageImpl::Activate  
 Der nächste Schritt besteht darin, die Eigenschaftenseite mit den Eigenschaftswerten des zugrunde liegenden Objekts zu initialisieren, wenn die Seite zum ersten Mal erstellt wird.  
  
 In diesem Fall sollten Sie die folgenden Member der Klasse hinzufügen, während Sie auch die Anfangswerte der Eigenschaft für den Vergleich verwenden, wenn Benutzer der Seite ihre Änderungen anwenden:  
  
 [!CODE [NVC_ATL_Windowing#77](../CodeSnippet/VS_Snippets_Cpp/NVC_ATL_Windowing#77)]  
  
 Die Basisklassenimplementierung der Methode [Aktivieren Sie](../Topic/IPropertyPageImpl::Activate.md) ist für das Erstellen des Dialogfelds und ihrer Steuerelemente verantwortlich, sodass Sie diese Methode überschreiben und eine eigene Initialisierung hinzufügen, nachdem Sie die Basisklasse aufgerufen haben:  
  
 [!CODE [NVC_ATL_Windowing#78](../CodeSnippet/VS_Snippets_Cpp/NVC_ATL_Windowing#78)]  
  
 Dieser Code verwendet die COM\-Methoden der **Document**\-Schnittstelle, um die Eigenschaften zu erhalten, die Sie sich interessieren.  Er verwendet dann die Win32 API\-Wrapper, die von [CDialogImpl](../atl/reference/cdialogimpl-class.md) und von den Basisklassen bereitgestellt werden, damit die Eigenschaftswerte für den Benutzer anzuzeigen.  
  
##  <a name="vcconoverride_ipropertypageimpl_apply"></a> Überschreiben von IPropertyPageImpl::Apply  
 Wenn Benutzer ihre Änderungen an Objekten anwenden möchten, ruft die Eigenschaftenseitensite die [Wenden Sie an](../Topic/IPropertyPageImpl::Apply.md)\-Methode auf.  Dies ist der Platz, um die Rückseite des Codes in **Activate** auszuführen \- während **Activate**\-Werte aus dem Objekt dauerte und in die Steuerelemente auf der Eigenschaftenseite hat, nimmt **Übernehmen**\-Werte von Steuerelementen auf der Eigenschaftenseite und legt sie in das Objekt.  
  
 [!CODE [NVC_ATL_Windowing#79](../CodeSnippet/VS_Snippets_Cpp/NVC_ATL_Windowing#79)]  
  
> [!NOTE]
>  Die Überprüfung anhand [m\_bDirty](../Topic/IPropertyPageImpl::m_bDirty.md) am Anfang dieser Implementierung ist eine ursprüngliche Überprüfung, um für unnötige Aktualisierungen der Objekte zu vermeiden, wenn **Übernehmen** mehrmals aufgerufen wird.  Es gibt auch Überprüfungen für jeden der Eigenschaftswerte, sicherzustellen, dass nur Änderungen Methodenaufruf zu **Document** führen.  
  
> [!NOTE]
>  **Document** macht **FullName** als schreibgeschützte Eigenschaft.  Um den Dateinamen des Dokuments auf Grundlage der Änderungen, die an der Eigenschaftenseite zu aktualisieren vorgenommen werden, müssen Sie die Methode verwenden **Speichern** um die Datei mit einem anderen Namen zu speichern.  Daher muss der Code in einer Eigenschaftenseite nicht zum Abrufen oder zum Festlegen von Eigenschaften beschränken.  
  
##  <a name="vccontesting_the_property_page"></a> Anzeigen der Eigenschaftenseite  
 Um diese Seite anzuzeigen, müssen Sie ein einfaches Hilfsobjekt erstellen.  Das Hilfsobjekt bietet eine Möglichkeit, die das **OleCreatePropertyFrame** API zum Anzeigen einer einzelnen Seite vereinfacht, die an ein einzelnes Objekt verbunden ist.  Diese Hilfe ist so konzipiert, dass sie aus Visual Basic verwendet werden kann.  
  
 Verwenden Sie [Fügen Sie Klassendialogfeld hinzu](../ide/add-class-dialog-box.md) und [ATL\-Assistent für einfache Objekte](../atl/reference/atl-simple-object-wizard.md), um eine neue Klasse zu generieren und `Helper` als Kurzname zu verwenden.  Einmal erstellt, fügen Sie eine Methode wie in der Tabelle unten dargestellt hinzu.  
  
|Element|Wert|  
|-------------|----------|  
|Methodenname|`ShowPage`|  
|Parameter|`[in] BSTR bstrCaption, [in] BSTR bstrID, [in] IUnknown* pUnk`|  
  
 Der `bstrCaption`\-Parameter ist die als Titel des Dialogfelds angezeigt werden Beschriftung.  Der `bstrID`\-Parameter ist eine Zeichenfolge, die entweder eine CLSID oder eine ProgID der Eigenschaftenseite darstellt, um anzuzeigen.  Der `pUnk`\-Parameter ist der `IUnknown` Zeiger des Objekts, dessen Eigenschaften über die Eigenschaftenseite konfiguriert werden.  
  
 Implementieren Sie die Methode wie unten dargestellt:  
  
 [!CODE [NVC_ATL_Windowing#80](../CodeSnippet/VS_Snippets_Cpp/NVC_ATL_Windowing#80)]  
  
##  <a name="vcconcreating_a_macro"></a> Erstellen eines Makros  
 Nachdem Sie das Projekt erstellt haben, können Sie die Eigenschaftenseite und das Hilfsobjekt mithilfe eines einfachen Makros testen, dass Sie in der Visual Studio\-Entwicklungsumgebung erstellen und ausführen können.  Dieses Makro erstellt ein Hilfsobjekt, ruft die **ShowPage**\-Methode mit dem ProgID der **DocProperties**\-Eigenschaftenseite und des **IUnknown** Zeigers des Dokuments derzeit aktiv im Visual Studio\-Editor auf.  Der Code, den Sie für dieses Makro erfordern, wird unten dargestellt:  
  
```  
Imports EnvDTE  
Imports System.Diagnostics  
  
Public Module AtlPages  
  
    Public Sub Test()  
        Dim Helper  
        Helper = CreateObject("ATLPages7.Helper.1")  
  
        On Error Resume Next  
        Helper.ShowPage( _  
            ActiveDocument.Name, _  
            "ATLPages7Lib.DocumentProperties.1", _  
            DTE.ActiveDocument _  
            )  
    End Sub  
  
End Module  
```  
  
 Wenn Sie dieses Makro ausführen, wird die Eigenschaftenseite den Dateinamen und den schreibgeschützten Status des aktiven Textdokuments nur für angezeigt.  Der schreibgeschützte Zustand des Dokuments gibt nur die Möglichkeit, dem Dokument in der Entwicklungsumgebung zu schreiben; sie wirkt sich nicht auf das Schreibschutzattribut der Datei auf dem Datenträger.  
  
## Siehe auch  
 [Eigenschaftenseiten](../atl/atl-com-property-pages.md)   
 [ATLPages\-Beispiel](../top/visual-cpp-samples.md)