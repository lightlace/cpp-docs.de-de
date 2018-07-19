---
title: Implementieren einer Eigenschaftenseite (ATL) | Microsoft-Dokumentation
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
ms.openlocfilehash: a4c7329e7784fc5228bca5aa5b167d04ded51aaf
ms.sourcegitcommit: 26fff80635bd1d51bc51899203fddfea8b29b530
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/05/2018
ms.locfileid: "37852274"
---
# <a name="example-implementing-a-property-page"></a>Beispiel: Das Implementieren einer Eigenschaftenseite
Dieses Beispiel zeigt, wie Sie auf einer Eigenschaftenseite zu erstellen, das Eigenschaften anzeigt (und können Sie ändern) die [Dokumentklassen](../mfc/document-classes.md) Schnittstelle.  
  
 Das Beispiel basiert auf der [ATLPages-Beispiel](../visual-cpp-samples.md).  
  
 Um dieses Beispiel abzuschließen, führen Sie folgende Aktionen ausführen:  
  
- [Hinzufügen von ATL-Eigenschaftenseitenklasse](#vcconusing_the_atl_object_wizard) über das Dialogfeld "Klasse hinzufügen" und die ATL-Eigenschaftenseiten-Assistent.  
  
- [Bearbeiten der Dialogfeldressource](#vcconediting_the_dialog_resource) durch Hinzufügen neuer Steuerelemente für die interessante Eigenschaften der `Document` Schnittstelle.  
  
- [Hinzufügen von meldungshandlern](#vcconadding_message_handlers) informiert Sie die Site der Seite zu der vom Benutzer vorgenommenen Änderungen.  
  
-   Fügen Sie einige `#import` Anweisungen und eine Typdefinition in der [Housekeeping](#vcconhousekeeping) Abschnitt.  
  
- [Überschreiben Sie IPropertyPageImpl::SetObjects](#vcconoverriding_ipropertypageimpl_setobjects) So überprüfen die Objekte, die auf der Eigenschaftenseite übergeben wird.  
  
- [Überschreiben Sie IPropertyPageImpl::Activate](#vcconoverriding_ipropertypageimpl_activate) auf der Eigenschaftenseite Schnittstelle zu initialisieren.  
  
- [Überschreiben Sie IPropertyPageImpl::Apply](#vcconoverride_ipropertypageimpl_apply) zum Aktualisieren des Objekts mit den neuesten Eigenschaftswerten.  
  
- [Zeigen Sie auf der Seite der](#vccontesting_the_property_page) durch Erstellen eines einfachen Hilfsprogramm-Objekts.  
  
- [Erstellen Sie ein Makro](#vcconcreating_a_macro) testen, die die Eigenschaftenseite.  
  
##  <a name="vcconusing_the_atl_object_wizard"></a> Der ATL-Eigenschaftenklasse von Seite hinzufügen  
 Erstellen Sie zunächst ein neues ATL-Projekt für eine DLL-Server namens `ATLPages7`. Verwenden Sie jetzt die [ATL-Eigenschaftenseiten-Assistent](../atl/reference/atl-property-page-wizard.md) auf einer Eigenschaftenseite zu generieren. Geben Sie die Eigenschaftenseite eine **Kurznamen** von **DocProperties** wechseln Sie zu der **Zeichenfolgen** Seite Eigenschaft-Seite-spezifische Elemente festlegen, wie in der folgenden Tabelle gezeigt.  
  
|Element|Wert|  
|----------|-----------|  
|Titel|TextDocument|  
|-Dokumentzeichenfolge|VCUE TextDocument-Eigenschaften|  
|HelpFile|*\<leer >*|  
  
 Die Werte, die Sie, auf dieser Seite des Assistenten festlegen auf der Seite Eigenschaftencontainer zurückgegeben, wenn ruft `IPropertyPage::GetPageInfo`. Was geschieht mit den Zeichenfolgen, nachdem das ist abhängig von den Container, aber sie in der Regel verwendet werden, werden um Ihre Seite für den Benutzer zu identifizieren. Der Titel in der Regel auf einer Registerkarte oberhalb der Seite angezeigt wird, und möglicherweise die Doc-Zeichenfolge in einer Statusleiste oder eine QuickInfo angezeigt (auch wenn der Frame Standardeigenschaft dieser Zeichenfolge überhaupt nicht verwendet).  
  
> [!NOTE]
>  Die Zeichenfolgen, die Sie hier festlegen, werden vom Assistenten als von Zeichenfolgenressourcen in Ihrem Projekt gespeichert. Sie können ganz einfach bearbeiten, dass diese Zeichenfolgen mit dem Ressourcen-Editor, wenn Sie benötigen diese Informationen ändern, nachdem der Code für Ihre Seite generiert wurde.  
  
 Klicken Sie auf **OK** , damit der Assistent die Eigenschaftenseite erstellt.  
  
##  <a name="vcconediting_the_dialog_resource"></a> Bearbeiten der Dialogfeldressource  
 Nun, dass Ihr Eigenschaftenseite generiert wurde, müssen Sie die Ressource Ihrer Seite darstellt, einige Steuerelemente hinzu. Fügen Sie ein Bearbeitungsfeld, ein statisches Textsteuerelement und ein Kontrollkästchen hinzu, und legen Sie deren IDs ein, wie unten dargestellt:  
  
 ![Dialogfeldressource bearbeiten](../atl/media/ppgresourcelabeled.gif "Ppgresourcelabeled")  
  
 Diese Steuerelemente werden verwendet werden, um den Dateinamen des Dokuments und den schreibgeschützten Status anzuzeigen.  
  
> [!NOTE]
>  Die Dialogressource umfasst keinen Frame Befehlsschaltflächen noch verfügt es über das Registerkartenformat aussehen, das Sie möglicherweise erwartet haben. Diese Funktionen werden bereitgestellt, durch eine eigenschaftenseitenrahmens z. B. die durch Aufrufen von erstellt [OleCreatePropertyFrame](http://msdn.microsoft.com/library/windows/desktop/ms678437).  
  
##  <a name="vcconadding_message_handlers"></a> Hinzufügen von Meldungshandlern  
 Mit den Steuerelementen vorhanden können Sie Meldungshandler aktualisieren Sie den geänderten Status der Seite aus, wenn der Wert der beiden Steuerelemente geändert wird, hinzufügen:  
  
 [!code-cpp[NVC_ATL_Windowing#73](../atl/codesnippet/cpp/example-implementing-a-property-page_1.h)]  
  
 Dieser Code reagiert auf Änderungen an das Kontrollkästchen "oder" Edit-Steuerelement durch Aufrufen von [:: SetDirty](../atl/reference/ipropertypageimpl-class.md#setdirty), die informiert, dass die Site der Seite, die die Seite geändert wurde. In der Regel reagiert die Site der Seite durch Aktivieren oder Deaktivieren einer **übernehmen** auf des eigenschaftenseitenrahmens auf die Schaltfläche.  
  
> [!NOTE]
>  Eigene Eigenschaftenseiten müssen Sie zum Nachverfolgen genau der Eigenschaften vom Benutzer geändert wurden, damit Sie vermeiden können, aktualisieren die Eigenschaften, die nicht geändert wurden. In diesem Beispiel implementiert diesen Code durch Nachverfolgen der die ursprünglichen Eigenschaftswerte und vergleichen diese mit den aktuellen Werten in der Benutzeroberfläche aus, wenn es darum, die Änderungen zu übernehmen.  
  
##  <a name="vcconhousekeeping"></a> Wartungsaufgaben  
 Fügen Sie nun eine Reihe von `#import` DocProperties.h-Anweisungen, damit der Compiler kennt die `Document` Schnittstelle:  
  
 [!code-cpp[NVC_ATL_Windowing#74](../atl/codesnippet/cpp/example-implementing-a-property-page_2.h)]  
  
 Sie müssen auch zum Verweisen auf die `IPropertyPageImpl` Basisklasse; fügen Sie die folgenden **Typedef** auf die `CDocProperties` Klasse:  
  
 [!code-cpp[NVC_ATL_Windowing#75](../atl/codesnippet/cpp/example-implementing-a-property-page_3.h)]  
  
##  <a name="vcconoverriding_ipropertypageimpl_setobjects"></a> IPropertyPageImpl::SetObjects überschreiben  
 Die erste `IPropertyPageImpl` Methode, die Sie überschreiben müssen, ist [SetObjects](../atl/reference/ipropertypageimpl-class.md#setobjects). Hier fügen Sie Code aus, um zu überprüfen, ob nur ein einzelnes Objekt übergeben wurde und sie unterstützt die `Document` -Schnittstelle, die Sie erwarten:  
  
 [!code-cpp[NVC_ATL_Windowing#76](../atl/codesnippet/cpp/example-implementing-a-property-page_4.h)]  
  
> [!NOTE]
>  Es ist sinnvoll, nur ein einzelnes Objekt für diese Seite zu unterstützen, da Sie den Benutzer, der Dateiname des Objekts festgelegt werden kann, nur eine Datei kann an jedem Speicherort vorhanden sein.  
  
##  <a name="vcconoverriding_ipropertypageimpl_activate"></a> IPropertyPageImpl::Activate überschreiben  
 Der nächste Schritt besteht, initialisieren die Eigenschaftenseite mit den Eigenschaftswerten des zugrunde liegenden Objekts aus, wenn die Seite zum ersten Mal erstellt wird.  
  
 In diesem Fall sollten Sie die folgenden Member der Klasse hinzufügen, da auch die anfänglichen Eigenschaftswerte für den Vergleich verwendet werden, wenn Benutzer die Seite ihre Änderungen zu übernehmen:  
  
 [!code-cpp[NVC_ATL_Windowing#77](../atl/codesnippet/cpp/example-implementing-a-property-page_5.h)]  
  
 Implementierung der Basisklasse, von der [aktivieren](../atl/reference/ipropertypageimpl-class.md#activate) Methode ist dafür verantwortlich, erstellen das Dialogfeld und seine Steuerelemente, damit Sie diese Methode überschreiben und Ihre eigenen Initialisierung nach dem Aufruf der Basisklasse hinzufügen können:  
  
 [!code-cpp[NVC_ATL_Windowing#78](../atl/codesnippet/cpp/example-implementing-a-property-page_6.h)]  
  
 Dieser Code verwendet die COM-Methoden von der `Document` Schnittstelle zum Abrufen der Eigenschaften, die Sie interessiert sind. Anschließend wird die Win32-API-Wrapper von bereitgestellten [CDialogImpl](../atl/reference/cdialogimpl-class.md) und deren Basisklassen, die Eigenschaftswerte für den Benutzer anzuzeigen.  
  
##  <a name="vcconoverride_ipropertypageimpl_apply"></a> IPropertyPageImpl::Apply überschreiben  
 Wenn Sie möchten, dass Benutzer ihre Änderungen auf die Objekte anzuwenden, ruft die Site der Seite die [übernehmen](../atl/reference/ipropertypageimpl-class.md#apply) Methode. Dies ist der Ort Sie das Gegenteil des Codes in `Activate` – während `Activate` dauerte Werte aus dem Objekt und die Steuerelemente auf der Eigenschaftenseite der Pushvorgang `Apply` akzeptiert Werte aus den Steuerelementen auf der Eigenschaftenseite und überträgt sie in der -Objekt.  
  
 [!code-cpp[NVC_ATL_Windowing#79](../atl/codesnippet/cpp/example-implementing-a-property-page_7.h)]  
  
> [!NOTE]
>  Die Überprüfung [M_bDirty](../atl/reference/ipropertypageimpl-class.md#m_bdirty) am Anfang dieser Implementierung wird eine anfängliche Überprüfung, um unnötige Updates von den Objekten zu vermeiden, wenn `Apply` mehr als einmal aufgerufen wird. Es gibt auch Überprüfungen im Hinblick auf jede der Eigenschaftswerte, um sicherzustellen, dass nur Änderungen in einem Methodenaufruf, führen die `Document`.  
  
> [!NOTE]
> `Document` macht `FullName` als nur-Lese Eigenschaft. Um den Dateinamen des Dokuments basierend auf Änderungen an die Eigenschaftenseite zu aktualisieren, müssen Sie mit der `Save` Methode zum Speichern der Datei mit einem anderen Namen. Daher der Code auf einer Eigenschaftenseite keine beschränken zum Abrufen oder Festlegen von Eigenschaften.  
  
##  <a name="vccontesting_the_property_page"></a> Anzeigen der Eigenschaftenseite  
 Um diese Seite anzeigen zu können, müssen Sie zum Erstellen eines einfachen Hilfsprogramm-Objekts. Das Hilfsobjekt bieten eine Methode, die vereinfacht die `OleCreatePropertyFrame` -API für das Anzeigen einer einzelnen Seite verbunden, auf ein einzelnes Objekt. Dieses Hilfsprogramm wird entworfen werden, sodass sie von Visual Basic verwendet werden kann.  
  
 Verwenden Sie die [Dialogfeld Klasse hinzufügen](../ide/add-class-dialog-box.md) und [ATL-Assistent für einfache Objekte](../atl/reference/atl-simple-object-wizard.md) eine neue Klasse zu generieren und verwenden `Helper` als kurze Namen. Nachdem Sie erstellt haben, fügen Sie eine Methode, wie in der folgenden Tabelle gezeigt.  
  
|Element|Wert|  
|----------|-----------|  
|Methodenname|`ShowPage`|  
|Parameter|`[in] BSTR bstrCaption, [in] BSTR bstrID, [in] IUnknown* pUnk`|  
  
 Die *BstrCaption* Parameter ist die Beschriftung, die als Titel des Dialogfelds angezeigt werden. Die *BstrID* Parameter ist eine Zeichenfolge, die entweder eine CLSID oder ProgID der Eigenschaftenseite angezeigt. Die *pUnk* Parameter werden die `IUnknown` -Zeiger des Objekts, dessen Eigenschaften werden auf der Seite der konfiguriert werden.  
  
 Implementieren Sie die Methode an, wie unten dargestellt:  
  
 [!code-cpp[NVC_ATL_Windowing#80](../atl/codesnippet/cpp/example-implementing-a-property-page_8.cpp)]  
  
##  <a name="vcconcreating_a_macro"></a> Erstellen eines Makros  
 Nachdem Sie das Projekt erstellt haben, können Sie testen die Eigenschaftenseite, und das Hilfsobjekt, der mithilfe eines einfachen Makros, das Sie erstellen und in der Visual Studio-Entwicklungsumgebung ausführen können. Erstellen Sie dieses Makro wird eine Hilfsprogramm Objekt aus, und rufen Sie dann die `ShowPage` Methode mit die ProgID des der **DocProperties** auf der Seite und die `IUnknown` Zeiger des Dokuments in Visual Studio-Editor gerade aktiv. Der Code, die, den Sie für dieses Makro benötigen, wird unten gezeigt:  
  
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
  
 Wenn Sie dieses Makro ausführen, wird die Eigenschaftenseite mit den Dateinamen und den schreibgeschützten Status des Dokuments derzeit aktiven Text angezeigt werden. Der schreibgeschützte Zustand des Dokuments reflektieren lediglich die Möglichkeit zum Schreiben in das Dokument in der Entwicklungsumgebung; Das Attribut "schreibgeschützt" der Datei auf dem Datenträger betroffen nicht.  
  
## <a name="see-also"></a>Siehe auch  
 [Eigenschaftenseiten](../atl/atl-com-property-pages.md)   
 [ATLPages-Beispiel](../visual-cpp-samples.md)

