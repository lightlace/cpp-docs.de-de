---
title: 'MFC-ActiveX-Steuerelemente: Lokalisieren eines ActiveX-Steuerelements | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
f1_keywords:
- LocaleID
- AfxOleRegisterTypeLib
dev_langs:
- C++
helpviewer_keywords:
- localization, ActiveX controls
- MFC ActiveX controls [MFC], localizing
- LocaleID ambient property [MFC]
- LOCALIZE sample [MFC]
ms.assetid: a44b839a-c652-4ec5-b824-04392708a5f9
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: b9a6495c23695f8cdedf45fbdd7cbc915b96873e
ms.sourcegitcommit: 060f381fe0807107ec26c18b46d3fcb859d8d2e7
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/25/2018
ms.locfileid: "36929607"
---
# <a name="mfc-activex-controls-localizing-an-activex-control"></a>MFC-ActiveX-Steuerelemente: Lokalisieren eines ActiveX-Steuerelements
Dieser Artikel beschreibt Verfahren zum Lokalisieren von ActiveX-Steuerelement-Schnittstellen.  
  
 Wenn Sie ein ActiveX-Steuerelement, um einen internationalen Markt anpassen möchten, empfiehlt es sich um das Steuerelement zu lokalisieren. Windows unterstützt viele Languages in Addition Standardsprache Englisch, Deutsch, Französisch und Schwedisch einschließlich. Dies kann Probleme für das Steuerelement darstellen, wenn die Schnittstelle nur auf Englisch ist.  
  
 ActiveX-Steuerelemente sollte im Allgemeinen immer ihre Gebietsschema auf der LocaleID-ambient-Eigenschaft basieren. Hierfür gibt es drei Möglichkeiten:  
  
-   Laden Sie die Ressourcen, die always on-Demand, basierend auf den aktuellen Wert der LocaleID-ambient-Eigenschaft. Die MFC-ActiveX-Steuerelemente Beispiel [LOCALIZE](../visual-cpp-samples.md) verwendet diese Strategie.  
  
-   Laden Sie Ressourcen aus, wenn das erste Steuerelement platziert wird, basierend auf der ambient LocaleID-Eigenschaft, und verwenden Sie diese Ressourcen für alle anderen Instanzen. In diesem Artikel wird diese Strategie.  
  
    > [!NOTE]
    >  Dies ist nicht in einigen Fällen funktionsfähig, wenn weitere Instanzen mit unterschiedlichen Gebietsschemas enthält.  
  
-   Verwenden der `OnAmbientChanged` Benachrichtigungsfunktion, um die richtigen Ressourcen für das Gebietsschema des Containers dynamisch zu laden.  
  
    > [!NOTE]
    >  Diese Methode kann für das Steuerelement verwendet, aber die DLL zur Laufzeit werden nicht dynamisch aktualisiert ihre eigenen Ressourcen bei Änderung die LocaleID-Ambiente-Eigenschaft. Laufzeit-DLLs für ActiveX-Steuerelemente verwenden darüber hinaus das Gebietsschema des Threads, um das Gebietsschema für die Ressourcen zu ermitteln.  
  
 Im weiteren Verlauf dieses Artikels werden zwei Lokalisierung von Strategien beschrieben. Die erste Strategie [zur Lokalisierung der Steuerelement-Programmierschnittstelle](#_core_localizing_your_control.92.s_programmability_interface) (Namen von Eigenschaften, Methoden und Ereignisse). Die zweite Strategie [zur Lokalisierung der Benutzeroberfläche des Steuerelements](#_core_localizing_the_control.92.s_user_interface), mithilfe des Containers Umgebungseigenschaft LocaleID-Wert. Ein Demo-Lokalisierung von Steuerelementen finden Sie in dem Beispiel für die MFC-ActiveX-Steuerelemente [LOCALIZE](../visual-cpp-samples.md).  
  
##  <a name="_core_localizing_your_control.92.s_programmability_interface"></a> Lokalisieren von Programmierschnittstelle des Steuerelements  
 Beim Lokalisieren von der Control-Programmierschnittstelle (die Schnittstelle, die Programmierer, die Schreiben von Anwendungen, die das Steuerelement zu verwenden), müssen Sie eine geänderte Version des Steuerelements erstellen. IDL-Datei (ein Skript zum Erstellen von Steuerelement-Typbibliothek) für jede Sprache, die Sie unterstützen möchten. Dies ist der einzige Ort, Sie die Steuerelement-Eigenschaftennamen zu lokalisieren müssen.  
  
 Wenn Sie einen lokalisierten-Steuerelement entwickeln, schließen Sie die Gebietsschema-ID als ein Attribut auf Typebene-Bibliothek. Wenn Sie eine Typbibliothek mit französischen Eigenschaftennamen bereitstellen möchten, stellen Sie beispielsweise eine Kopie Ihrer Beispiel. IDL-Datei, und nennen Sie es SAMPLEFR. IDL. Fügen Sie eine Gebietsschema-ID-Attribut in der Datei (die Gebietsschema-ID für Französisch ist 0x040c), ähnlich der folgenden:  
  
 [!code-cpp[NVC_MFC_AxLoc#1](../mfc/codesnippet/cpp/mfc-activex-controls-localizing-an-activex-control_1.idl)]  
  
 Ändern Sie die Eigenschaftennamen im SAMPLEFR. IDL für ihre Entsprechungen für Französisch und verwenden Sie dann MKTYPLIB. EXE-Datei, die französische Typbibliothek SAMPLEFR. TLB.  
  
 Um mehrere lokalisierte Typbibliotheken zu erstellen, können Sie eine lokalisierte hinzufügen. IDL-Dateien zum Projekt, und sie werden automatisch erstellt werden.  
  
#### <a name="to-add-an-idl-file-to-your-activex-control-project"></a>Hinzufügen einer. IDL-Datei dem ActiveX-Steuerelement-Projekt  
  
1.  Mit dem Steuerelementprojekt geöffnet ist, auf die **Projekt** Menü klicken Sie auf **vorhandenes Element hinzufügen**.  
  
     Die **vorhandenes Element hinzufügen** Dialogfeld wird angezeigt.  
  
2.  Aktivieren Sie bei Bedarf das Laufwerk und Verzeichnis anzeigen.  
  
3.  In der **Dateityp** wählen Sie im **alle Dateien (\*.\*)** .  
  
4.  Klicken Sie im Listenfeld Datei doppelklicken Sie auf die. IDL-Datei, die Sie in das Projekt einfügen möchten.  
  
5.  Klicken Sie auf **öffnen** Wenn Sie alle notwendigen hinzugefügt haben. IDL-Dateien.  
  
 Da die Dateien zum Projekt hinzugefügt wurden, werden sie erstellt werden, wenn der Rest des Projekts basiert. Die lokalisierte Typbibliotheken befinden sich im aktuellen Verzeichnis der ActiveX-Steuerelement-Projekt.  
  
 Innerhalb des Codes, die interne Eigenschaften-Namen (normalerweise in Englisch) werden immer verwendet und sind nicht lokalisiert. Dies schließt Dispatchzuordnung des Steuerelements, das Exchange-Eigenschaftenfunktionen und Codes Exchange Seite Eigenschaft.  
  
 Nur eine Typbibliothek (. TLB)-Datei in die Ressourcen der Implementierung des Steuerelements gebunden werden kann (. OCX)-Datei. Dies ist normalerweise die Version mit standardisierten (in der Regel auf Englisch) Namen. So liefern Sie eine lokalisierte Version des Steuerelements Sie liefern müssen die. OCX (die bereits auf den Standardwert gebunden wurde. TLB-Version) und die. TLB für das entsprechende Gebietsschema. Dies bedeutet, dass nur die. OCX ist seit den richtigen für englische Versionen erforderlich. TLB wurde bereits an es gebunden. Für andere Gebietsschemas, die lokalisierte Typbibliothek auch geliefert werden muss mit der. OCX.  
  
 Um sicherzustellen, dass die Clients des Steuerelements die lokalisierte Typbibliothek finden können, registrieren Sie Ihr Gebietsschema. Klicken Sie im Abschnitt "TypeLib" von der Windows-systemregistrierung TLB-Dateien. Der dritte Parameter (normalerweise optional) die [AfxOleRegisterTypeLib](../mfc/reference/registering-ole-controls.md#afxoleregistertypelib) Funktion wird für diesen Zweck bereitgestellt. Das folgende Beispiel registriert eine französische Typbibliothek für ein ActiveX-Steuerelement:  
  
 [!code-cpp[NVC_MFC_AxLoc#2](../mfc/codesnippet/cpp/mfc-activex-controls-localizing-an-activex-control_2.cpp)]  
  
 Wenn das Steuerelement registriert wird, die `AfxOleRegisterTypeLib` Funktion sucht automatisch nach dem angegebenen. TLB-Datei im gleichen Verzeichnis wie das Steuerelement und registriert ihn in der Datenbank der Windows-Registrierung. Wenn die. TLB-Datei nicht gefunden wird, die Funktion hat keine Auswirkungen.  
  
##  <a name="_core_localizing_the_control.92.s_user_interface"></a> Lokalisieren die Steuerelement-Benutzeroberfläche  
 Um ein Steuerelement-Benutzeroberfläche zu lokalisieren, platzieren Sie alle Benutzer sichtbare des Steuerelements-Ressourcen (z. B. Eigenschaftenseiten und Fehlermeldungen) in sprachspezifischen Ressourcen-DLLs aus. Der Container Umgebungseigenschaft LocaleID-Wert können dann wählen Sie die entsprechende DLL für das Gebietsschema des Benutzers.  
  
 Das folgende Codebeispiel veranschaulicht eine Möglichkeit zum Suchen und laden die Ressourcen-DLL für ein bestimmtes Gebietsschema. Diese Memberfunktion aufgerufen `GetLocalizedResourceHandle` in diesem Beispiel kann eine Memberfunktion der ActiveX-Steuerelementklasse sein:  
  
 [!code-cpp[NVC_MFC_AxLoc#3](../mfc/codesnippet/cpp/mfc-activex-controls-localizing-an-activex-control_3.cpp)]  
  
 Beachten Sie, dass die untersprachen-ID in jedem Fall der Switch-Anweisung, um spezialisierter Lokalisierung bereitzustellen überprüft werden konnte. Eine Veranschaulichung dieser Funktion finden Sie unter der `GetResourceHandle` -Funktion in der MFC-ActiveX-Steuerelemente Beispiel [LOCALIZE](../visual-cpp-samples.md).  
  
 Wenn das Steuerelement zunächst selbst in einen Container geladen wird, rufen sie [COleControl:: AmbientLocaleID](../mfc/reference/colecontrol-class.md#ambientlocaleid) zum Abrufen der Gebietsschema-ID. Das Steuerelement kann dann den zurückgegebenen Gebietsschema-ID-Wert zu übergeben, die `GetLocalizedResourceHandle` -Funktion, die die richtige Ressourcenbibliothek geladen. Das Steuerelement sollte das resultierende Handle übergeben, sofern vorhanden, um [AfxSetResourceHandle](../mfc/reference/application-information-and-management.md#afxsetresourcehandle):  
  
 [!code-cpp[NVC_MFC_AxLoc#4](../mfc/codesnippet/cpp/mfc-activex-controls-localizing-an-activex-control_4.cpp)]  
  
 Versetzen Sie das Codebeispiel oben in einer Memberfunktion des Steuerelements, wie z. B. eine Überschreibung der [COleControl:: OnSetClientSite](../mfc/reference/colecontrol-class.md#onsetclientsite). Darüber hinaus *M_hResDLL* sollte eine Membervariable der Steuerelementklasse sein.  
  
 Ähnlichen Logik können Sie zum Lokalisieren von Eigenschaftenseite des Steuerelements. Um die Eigenschaftenseite zu lokalisieren, fügen Sie Code ähnlich dem folgenden Beispiel Implementierungsdatei der Eigenschaftenseite (in einer Überschreibung von [COlePropertyPage:: OnSetPageSite](../mfc/reference/colepropertypage-class.md#onsetpagesite)):  
  
 [!code-cpp[NVC_MFC_AxLoc#5](../mfc/codesnippet/cpp/mfc-activex-controls-localizing-an-activex-control_5.cpp)]  
  
## <a name="see-also"></a>Siehe auch  
 [MFC-ActiveX-Steuerelemente](../mfc/mfc-activex-controls.md)

