---
title: Implementieren einer Eigenschaftenseite (ATL) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- property pages, implementing
ms.assetid: c30b67fe-ce08-4249-ae29-f3060fa8d61e
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 139bdd9076e99139f4da105b4bb2b375689efe15
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
---
# <a name="example-implementing-a-property-page"></a>Beispiel: Implementieren einer Eigenschaftenseite
In diesem Beispiel wird gezeigt, wie eine Eigenschaftenseite erstellt, die Eigenschaften des anzeigt (und können Sie ändern) die [Dokumentklassen](../mfc/document-classes.md) Schnittstelle.  
  
 Das Beispiel basiert auf der [ATLPages-Beispiel](../visual-cpp-samples.md).  
  
 Um dieses Beispiel zu vervollständigen, führen Sie folgende Aktionen ausführen:  
  
- [Hinzufügen der ATL-Eigenschaftenklasse von Seite](#vcconusing_the_atl_object_wizard) verwenden das Dialogfeld "Klasse hinzufügen" und die ATL-Eigenschaftenseiten-Assistent.  
  
- [Bearbeiten Sie die Dialogfeldressource](#vcconediting_the_dialog_resource) durch Hinzufügen neuer Steuerelemente für die interessanten Eigenschaften der **Dokument** Schnittstelle.  
  
- [Hinzufügen von meldungshandlern](#vcconadding_message_handlers) , behalten Sie die Site der Eigenschaft Seite informiert, der vom Benutzer vorgenommene Änderungen.  
  
-   Fügen Sie einige `#import` Anweisungen und eine Typdefinition in der [Housekeeping](#vcconhousekeeping) Abschnitt.  
  
- [Überschreiben Sie IPropertyPageImpl::SetObjects](#vcconoverriding_ipropertypageimpl_setobjects) So überprüfen Sie die Objekte, die auf der Eigenschaftenseite übergeben werden.  
  
- [Überschreiben Sie IPropertyPageImpl::Activate](#vcconoverriding_ipropertypageimpl_activate) der Eigenschaftenseite-Schnittstelle nicht initialisieren.  
  
- [Überschreiben Sie IPropertyPageImpl::Apply](#vcconoverride_ipropertypageimpl_apply) zum Aktualisieren des Objekts mit den aktuellen Eigenschaftswerten.  
  
- [Anzeigen die Eigenschaftenseite](#vccontesting_the_property_page) durch Erstellen eines einfachen Hilfsprogramm-Objekts.  
  
- [Erstellen Sie ein Makro](#vcconcreating_a_macro) testen, die die Eigenschaftsseite ".  
  
##  <a name="vcconusing_the_atl_object_wizard"></a> Hinzufügen von ATL-Eigenschaft-Page-Klasse  
 Erstellen Sie zunächst ein neues ATL-Projekt für eine DLL-Server namens `ATLPages7`. Verwenden Sie jetzt die [ATL-Eigenschaftenseiten-Assistent](../atl/reference/atl-property-page-wizard.md) auf eine Eigenschaftenseite zu generieren. Geben Sie die Eigenschaftenseite ein **Kurzname** von **DocProperties** wechseln Sie zu der **Zeichenfolgen** Seite Eigenschaft-Seite-spezifische Elemente festlegen, wie in der folgenden Tabelle gezeigt.  
  
|Element|Wert|  
|----------|-----------|  
|Titel|TextDocument|  
|Doc-Zeichenfolge|VCUE TextDocument-Eigenschaften|  
|HelpFile|*\<leere >*|  
  
 Die Werte, die Sie auf dieser Seite des Assistenten legen Sie für den Container der Eigenschaft Seite zurückgesendet, nachdem ruft **IPropertyPage::GetPageInfo**. Was geschieht mit den Zeichenfolgen nach, die den Container abhängig ist, aber sie in der Regel verwendet werden, werden um die Seite für den Benutzer zu identifizieren. Der Titel wird in der Regel auf einer Registerkarte oberhalb der Seite angezeigt, und die Doc-Zeichenfolge kann in einer Statusleiste oder eine QuickInfo angezeigt werden (obwohl die Standardeigenschaft Frame dieser Zeichenfolge überhaupt nicht verwendet).  
  
> [!NOTE]
>  Die Zeichenfolgen, die Sie hier festlegen, werden vom Assistenten als Zeichenfolgenressourcen in Ihrem Projekt gespeichert. Sie können problemlos bearbeiten diese Zeichenfolgen mit dem Ressourcen-Editor, wenn Sie benötigen diese Informationen ändern, nachdem der Code für die Seite generiert wurde.  
  
 Klicken Sie auf **OK** damit der Assistent die Eigenschaftenseite zu generieren.  
  
##  <a name="vcconediting_the_dialog_resource"></a> Bearbeiten die Dialogfeldressource  
 Nun, dass die Eigenschaftenseite generiert wurde, müssen Sie die Dialogressource Ihre Seite darstellt, einige Steuerelemente hinzufügen. Fügen Sie ein Eingabefeld, einem statischen Textsteuerelement und ein Kontrollkästchen hinzu, und legen Sie deren IDs aus, wie unten dargestellt:  
  
 ![Dialogfeldressource bearbeiten](../atl/media/ppgresourcelabeled.gif "Ppgresourcelabeled")  
  
 Diese Steuerelemente werden verwendet werden, um den Dateinamen des Dokuments und den schreibgeschützten Status anzuzeigen.  
  
> [!NOTE]
>  Die Dialogressource eine Befehlsschaltflächen Frame nicht einschließt, und weist auch nicht im Registerkartenformat suchen, die Sie möglicherweise erwartet haben. Diese Funktionen werden bereitgestellt, von einem Eigenschaft-Seitenrahmen z. B. durch Aufrufen von erstellt [OleCreatePropertyFrame](http://msdn.microsoft.com/library/windows/desktop/ms678437).  
  
##  <a name="vcconadding_message_handlers"></a> Hinzufügen von Meldungshandlern  
 Mit der Kontrollmechanismen implementiert können Sie die Message-Handler, um den geänderten Status der Seite zu aktualisieren, bei Änderung des Werts eines der Steuerelemente hinzufügen:  
  
 [!code-cpp[NVC_ATL_Windowing#73](../atl/codesnippet/cpp/example-implementing-a-property-page_1.h)]  
  
 Dieser Code reagiert auf Änderungen, die durch den Aufruf an den Edit-Steuerelement oder das Kontrollkästchen [:: SetDirty](../atl/reference/ipropertypageimpl-class.md#setdirty), dem informiert, dass der Seite-Website, die die Seite geändert wurde. In der Regel wird die Seite-Website reagieren, indem aktivieren oder Deaktivieren einer **übernehmen** Schaltfläche auf der Seite Eigenschaft-Frame.  
  
> [!NOTE]
>  In eine eigene Eigenschaftenseiten müssen Sie zum Nachverfolgen von genau die Eigenschaften vom Benutzer geändert wurden, damit Sie vermeiden können, aktualisieren die Eigenschaften, die nicht geändert wurden. In diesem Beispiel implementiert diesen Code Nachverfolgen der die ursprünglichen Eigenschaftswerte, und vergleichen diese mit den aktuellen Werten aus der Benutzeroberfläche aus, wenn die Änderungen angewendet werden.  
  
##  <a name="vcconhousekeeping"></a> Housekeeping  
 Fügen Sie nun eine Reihe von `#import` DocProperties.h-Anweisungen, damit der Compiler kennt die **Dokument** Schnittstelle:  
  
 [!code-cpp[NVC_ATL_Windowing#74](../atl/codesnippet/cpp/example-implementing-a-property-page_2.h)]  
  
 Sie müssen auch zum Verweisen auf die `IPropertyPageImpl` Basisklasse; fügen Sie die folgenden `typedef` auf die **CDocProperties** Klasse:  
  
 [!code-cpp[NVC_ATL_Windowing#75](../atl/codesnippet/cpp/example-implementing-a-property-page_3.h)]  
  
##  <a name="vcconoverriding_ipropertypageimpl_setobjects"></a> IPropertyPageImpl::SetObjects überschreiben  
 Die erste `IPropertyPageImpl` -Methode, die Sie überschreiben müssen, ist [SetObjects](../atl/reference/ipropertypageimpl-class.md#setobjects). Hier fügen Sie Code, um zu überprüfen, dass nur ein einzelnes Objekt übergeben wurde und dass es unterstützt die **Dokument** Schnittstelle, die Sie erwarten:  
  
 [!code-cpp[NVC_ATL_Windowing#76](../atl/codesnippet/cpp/example-implementing-a-property-page_4.h)]  
  
> [!NOTE]
>  Es ist sinnvoll, nur ein einzelnes Objekt für diese Seite zu unterstützen, da Sie den Benutzer, der den Dateinamen des Objekts festgelegt werden kann – nur eine Datei kann an jedem Speicherort vorhanden sein.  
  
##  <a name="vcconoverriding_ipropertypageimpl_activate"></a> IPropertyPageImpl::Activate überschreiben  
 Der nächste Schritt besteht, initialisieren die Eigenschaftenseite mit den Eigenschaftswerten des zugrunde liegenden Objekts ein, wenn die Seite zum ersten Mal erstellt wird.  
  
 In diesem Fall sollten Sie die folgenden Member der Klasse hinzufügen, da auch die anfänglichen Eigenschaftenwerte für den Vergleich verwendet werden, wenn auf der Seite Benutzer ihre Änderungen zu übernehmen:  
  
 [!code-cpp[NVC_ATL_Windowing#77](../atl/codesnippet/cpp/example-implementing-a-property-page_5.h)]  
  
 Die basisklassenimplementierung der [aktivieren](../atl/reference/ipropertypageimpl-class.md#activate) Methode ist verantwortlich für das Erstellen des Dialogfelds "" und seine Steuerelemente, damit Sie diese Methode überschreiben und eine eigene Initialisierung nach dem Aufruf der Basisklasse hinzufügen können:  
  
 [!code-cpp[NVC_ATL_Windowing#78](../atl/codesnippet/cpp/example-implementing-a-property-page_6.h)]  
  
 Dieser Code verwendet die COM-Methoden von der **Dokument** Schnittstelle zum Abrufen der Eigenschaften, die Sie interessiert sind. Es verwendet dann die Win32-API-Wrapper gebotenen [CDialogImpl](../atl/reference/cdialogimpl-class.md) und deren Basisklassen auf die Eigenschaftswerte für den Benutzer anzuzeigen.  
  
##  <a name="vcconoverride_ipropertypageimpl_apply"></a> IPropertyPageImpl::Apply überschreiben  
 Wenn Sie möchten, dass Benutzer ihre Änderungen auf die Objekte anzuwenden, ruft die Site der Eigenschaft Seite der [übernehmen](../atl/reference/ipropertypageimpl-class.md#apply) Methode. Dies ist der Speicherort des Codes in umgekehrt Verfahren **aktivieren** – während **aktivieren** übernahm von Werten aus dem Objekt und übertragen Sie sie in die Steuerelemente auf der Eigenschaftenseite **übernehmen** akzeptiert die Werte aus den Steuerelementen auf der Eigenschaftenseite und stellt diese in das Objekt.  
  
 [!code-cpp[NVC_ATL_Windowing#79](../atl/codesnippet/cpp/example-implementing-a-property-page_7.h)]  
  
> [!NOTE]
>  Die Überprüfung [M_bDirty](../atl/reference/ipropertypageimpl-class.md#m_bdirty) am Anfang dieser Implementierung wird eine anfängliche Überprüfung um unnötige Updates von Objekten zu vermeiden, wenn **übernehmen** mehr als einmal aufgerufen wird. Es gibt auch Überprüfungen für alle Eigenschaftswerte, um sicherzustellen, dass nur Änderungen in einem Methodenaufruf zu führen, dass die **Dokument**.  
  
> [!NOTE]
> **Dokument** macht **FullName** als nur-Lese Eigenschaft. Um den Dateinamen des Dokuments basierend auf Änderungen an die Eigenschaftenseite zu aktualisieren, müssen Sie die **speichern** Methode zum Speichern der Datei mit einem anderen Namen. Daher der Code auf einer Eigenschaftenseite nicht ausgeschlossen, dass selbst zum Abrufen oder Festlegen von Eigenschaften.  
  
##  <a name="vccontesting_the_property_page"></a> Anzeigen der Eigenschaftenseite  
 Um diese Seite anzuzeigen, müssen Sie ein einfaches Hilfsobjekt zu erstellen. Das Hilfsobjekt bietet eine Methode, die vereinfacht die **OleCreatePropertyFrame** API für die Anzeige von einer einzelnen Seite mit einem einzelnen Objekt verbunden. Dieses Hilfsprogramm wird entworfen werden, sodass sie aus Visual Basic verwendet werden kann.  
  
 Verwenden Sie die [Klasse hinzufügen (Dialogfeld)](../ide/add-class-dialog-box.md) und [ATL-Assistent für einfache Objekte](../atl/reference/atl-simple-object-wizard.md) zum Generieren einer neuen Klasse und verwenden `Helper` als kurze Namen. Nach der Erstellung, fügen Sie eine Methode hinzu, wie in der folgenden Tabelle gezeigt.  
  
|Element|Wert|  
|----------|-----------|  
|Methodenname|`ShowPage`|  
|Parameter|`[in] BSTR bstrCaption, [in] BSTR bstrID, [in] IUnknown* pUnk`|  
  
 Die `bstrCaption` Parameter ist die Beschriftung ein, die als Titel des Dialogfelds angezeigt werden. Die `bstrID` Parameter ist eine Zeichenfolge, die entweder eine CLSID oder ProgID der Eigenschaftenseite angezeigt. Die `pUnk` Parameter werden die `IUnknown` Zeiger des Objekts, dessen Eigenschaften die Eigenschaftenseite konfiguriert werden werden.  
  
 Implementieren Sie die Methode aus, wie unten dargestellt:  
  
 [!code-cpp[NVC_ATL_Windowing#80](../atl/codesnippet/cpp/example-implementing-a-property-page_8.cpp)]  
  
##  <a name="vcconcreating_a_macro"></a> Erstellen ein Makro  
 Nachdem Sie das Projekt erstellt haben, können Sie testen die Eigenschaftsseite "und das Hilfsobjekt mithilfe eines einfachen Makros, das Sie erstellen können, und führen Sie in der Visual Studio-Entwicklungsumgebung. Erstellen Sie dieses Makro wird eine Hilfsprogramm-Objekt, und rufen Sie dann seine **ShowPage** Methode mit die ProgID des der **DocProperties** Eigenschaftenseite und die **IUnknown** Zeiger des Dokuments aktuell in der Visual Studio-Editor aktiv. Der Code, den Sie für dieses Makro müssen, wird unten gezeigt:  
  
```  
Imports EnvDTE  
Imports System.Diagnostics  
 
Public Module AtlPages  
 
    Public Sub Test()  
    Dim Helper  
    Helper = CreateObject("ATLPages7.Helper.1")  
 
    On Error Resume Next  
    Helper.ShowPage(_ 
    ActiveDocument.Name,
    _ 
 "ATLPages7Lib.DocumentProperties.1",
    _ 
    DTE.ActiveDocument _)  
    End Sub  
 
End Module  
```  
  
 Wenn Sie dieses Makro ausführen, wird die Eigenschaftenseite mit den Dateinamen und den schreibgeschützten Status des derzeit aktiven Textdokuments angezeigt werden. Der schreibgeschützte Status des Dokuments reflektieren lediglich die Berechtigung zum Schreiben in das Dokument in der Entwicklungsumgebung; Er wirkt sich nicht das Schreibschutzattribut der Datei auf dem Datenträger aus.  
  
## <a name="see-also"></a>Siehe auch  
 [Eigenschaftenseiten](../atl/atl-com-property-pages.md)   
 [ATLPages-Beispiel](../visual-cpp-samples.md)

