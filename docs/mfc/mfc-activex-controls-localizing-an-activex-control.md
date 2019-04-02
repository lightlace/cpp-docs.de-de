---
title: 'MFC-ActiveX-Steuerelemente: Lokalisieren eines ActiveX-Steuerelements'
ms.date: 09/12/2018
f1_keywords:
- LocaleID
- AfxOleRegisterTypeLib
helpviewer_keywords:
- localization, ActiveX controls
- MFC ActiveX controls [MFC], localizing
- LocaleID ambient property [MFC]
- LOCALIZE sample [MFC]
ms.assetid: a44b839a-c652-4ec5-b824-04392708a5f9
ms.openlocfilehash: 13c8ff545763017b01685e012ab2d497eaf7084a
ms.sourcegitcommit: 5cecccba0a96c1b4ccea1f7a1cfd91f259cc5bde
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/01/2019
ms.locfileid: "58767547"
---
# <a name="mfc-activex-controls-localizing-an-activex-control"></a>MFC-ActiveX-Steuerelemente: Lokalisieren eines ActiveX-Steuerelements

Dieser Artikel beschreibt Verfahren zum Lokalisieren von ActiveX-Steuerelement-Schnittstellen.

>[!IMPORTANT]
> ActiveX ist eine veraltete Technologie, die nicht für Neuentwicklungen verwendet werden soll. Weitere Informationen zu moderne Technologien, die ActiveX-ablösen, finden Sie unter [ActiveX-Steuerelemente](activex-controls.md).

Wenn Sie ein ActiveX-Steuerelement einen internationalen Markt anpassen möchten, empfiehlt es sich um das Steuerelement zu lokalisieren. Windows unterstützt viele Sprachen zusätzlich zu den Englisch, darunter Deutsch, Französisch und Schwedisch. Dies kann Probleme für das Steuerelement darstellen, wenn die Schnittstelle nur auf Englisch ist.

Im Allgemeinen sollte ActiveX-Steuerelemente immer ihrem Gebietsschema auf die LocaleID-ambient-Eigenschaft basieren. Hierfür gibt es drei Möglichkeiten:

- Laden Sie die Ressourcen, die immer bei Bedarf, basierend auf den aktuellen Wert von der LocaleID-ambient-Eigenschaft. Die MFC-ActiveX-Steuerelemente Beispiel [LOCALIZE](../overview/visual-cpp-samples.md) nutzt diese Strategie.

- Laden Sie Ressourcen aus, wenn das erste Steuerelement basierend auf der ambient LocaleID-Eigenschaft Instanzen wird, und verwenden Sie diese Ressourcen für alle anderen Instanzen. In diesem Artikel wird diese Strategie.

    > [!NOTE]
    >  Diese funktioniert nicht ordnungsgemäß in einigen Fällen, wenn zukünftige Instanzen mit unterschiedlichen Gebietsschemas enthält.

- Verwenden der `OnAmbientChanged` Notification-Funktion, um die richtigen Ressourcen für das Gebietsschema des Containers dynamisch zu laden.

    > [!NOTE]
    >  Dies funktioniert für das Steuerelement, aber die Laufzeit-DLL dynamisch aktualisiert nicht seine eigenen Ressourcen bei die LocaleID-Ambiente-Eigenschaft ändert. Laufzeit-DLLs für ActiveX-Steuerelemente verwenden darüber hinaus das Threadgebietsschema, um das Gebietsschema für ihre Ressourcen zu ermitteln.

Im weiteren Verlauf dieses Artikels werden zwei Lokalisierung von Strategien beschrieben. Die erste Strategie [ordnet Programmierschnittstelle des Steuerelements](#_core_localizing_your_control.92.s_programmability_interface) (Namen von Eigenschaften, Methoden und Ereignisse). Die zweite Strategie [ordnet die Benutzeroberfläche des Steuerelements](#_core_localizing_the_control.92.s_user_interface), verwenden ambient LocaleID-Eigenschaft des Containers. Eine Demonstration der steuerelementlokalisierung finden Sie unter dem Beispiel für die MFC-ActiveX-Steuerelemente [LOCALIZE](../overview/visual-cpp-samples.md).

##  <a name="_core_localizing_your_control.92.s_programmability_interface"></a> Lokalisieren von Programmierschnittstelle des Steuerelements

Beim Lokalisieren von des Steuerelements-Programmierschnittstelle (die Schnittstelle, die Programmierer, die Schreiben von Anwendungen, die das Steuerelement zu verwenden), müssen Sie eine geänderte Version des Steuerelements erstellen. IDL-Datei (ein Skript zum Erstellen der Steuerelement-Typbibliothek) für jede Sprache, die Sie unterstützen möchten. Dies ist der einzige Ort, Sie den Namen der Steuerelementeigenschaften zu lokalisieren müssen.

Wenn Sie einem lokalisierten-Steuerelement entwickeln, schließen Sie die Gebietsschema-ID als ein Attribut auf Typebene-Bibliothek ein. Wenn Sie eine Typbibliothek mit französischen Eigenschaftennamen bereitstellen möchten, erstellen Sie z. B. eine Kopie des BEISPIELS. IDL-Datei, und rufen Sie es SAMPLEFR. IDL. Fügen Sie ein Gebietsschema-ID-Attribut in der Datei (die Gebietsschema-ID für Französisch ist 0x040c), etwa wie folgt:

[!code-cpp[NVC_MFC_AxLoc#1](../mfc/codesnippet/cpp/mfc-activex-controls-localizing-an-activex-control_1.idl)]

Ändern Sie die Eigenschaftennamen in SAMPLEFR. IDL auf französische Entsprechungen und verwenden Sie dann MKTYPLIB. EXE-Datei die französische Typbibliothek SAMPLEFR. TLB.

Um mehrere lokalisierte Typbibliotheken zu erstellen, können Sie eine lokalisierte hinzufügen. IDL-Dateien zum Projekt, und sie werden automatisch erstellt werden.

#### <a name="to-add-an-idl-file-to-your-activex-control-project"></a>Hinzufügen einer. IDL-Datei zu dem ActiveX-Steuerelementprojekt

1. Mit das Projekt geöffnet ist, auf die **Projekt** Menü klicken Sie auf **vorhandenes Element hinzufügen**.

   Die **vorhandenes Element hinzufügen** Dialogfeld wird angezeigt.

1. Wählen Sie das Laufwerk und Verzeichnis, um anzuzeigen, bei Bedarf.

1. In der **Dateityp** Kontrollkästchen **alle Dateien (\*.\*)** .

1. Doppelklicken Sie im Listenfeld Datei auf den. IDL-Datei, die Sie in das Projekt einfügen möchten.

1. Klicken Sie auf **öffnen** Wenn Sie alle erforderlichen hinzugefügt haben. IDL-Dateien.

Da die Dateien zum Projekt hinzugefügt wurden, werden sie erstellt werden, wenn der Rest des Projekts erstellt wird. Die lokalisierte Typbibliotheken befinden sich in dem aktuellen Projektverzeichnis für ActiveX-Steuerelement.

Innerhalb des Codes die interne Eigenschaften-Namen (normalerweise in englischer Sprache) werden immer verwendet und sind nicht lokalisiert. Dies schließt Dispatchzuordnung des Steuerelements, die Exchange-Eigenschaftenfunktionen und Ihre Eigenschaft Seite Data Exchange-Code.

Nur eine Typbibliothek (. TLB)-Datei in die Ressourcen von der Implementierung des Steuerelements gebunden werden kann (. OCX)-Datei. Dies ist normalerweise die Version mit der standardisierten (in der Regel auf Englisch) Namen. Eine lokalisierte Version des Steuerelements zu senden, Sie für den Versand müssen, der. OCX (die auf den Standardwert bereits gebunden wurde. TLB-Version) und die. TLB für das jeweilige Gebietsschema. Dies bedeutet, dass nur die. OCX ist seit den richtigen für englische Versionen erforderlich. TLB wurde bereits an sie gebunden. Für andere Gebietsschemas, die lokalisierte Typbibliothek auch geliefert werden muss mit den. OCX.

Um sicherzustellen, dass die Clients des Steuerelements auf die Bibliothek mit lokalisierten finden können, registrieren Sie Ihr Gebietsschema aus. Im Abschnitt "Typbibliothek" der Windows-systemregistrierung TLB-Dateien. Der dritte Parameter (normalerweise optional) der der [AfxOleRegisterTypeLib](../mfc/reference/registering-ole-controls.md#afxoleregistertypelib) Funktion wird für diesen Zweck bereitgestellt. Im folgende Beispiel wird eine französische Typbibliothek für ActiveX-Steuerelement registriert:

[!code-cpp[NVC_MFC_AxLoc#2](../mfc/codesnippet/cpp/mfc-activex-controls-localizing-an-activex-control_2.cpp)]

Wenn das Steuerelement registriert ist, die `AfxOleRegisterTypeLib` Funktion sucht automatisch nach dem angegebenen. TLB-Datei im gleichen Verzeichnis wie das Steuerelement und registriert sie in der Datenbank der Windows-Registrierung. Wenn die. TLB-Datei nicht gefunden wird, die Funktion hat keine Auswirkungen.

##  <a name="_core_localizing_the_control.92.s_user_interface"></a> Lokalisieren die Benutzeroberfläche des Steuerelements

Um die Benutzeroberfläche des Steuerelements zu lokalisieren, platzieren Sie aller Benutzer sichtbare des Steuerelements-Ressourcen (z. B. Eigenschaftenseiten und Fehlermeldungen) in sprachspezifischen Ressourcen-DLLs. Sie können dann ambient LocaleID-Eigenschaft des Containers verwenden, Auswahl die entsprechenden DLL für das Gebietsschema des Benutzers.

Das folgende Codebeispiel veranschaulicht eine Möglichkeit zum Suchen und laden die Ressourcen-DLL für ein bestimmtes Gebietsschema. Diese Memberfunktion auf, dem Namen `GetLocalizedResourceHandle` für dieses Beispiel kann eine Memberfunktion der ActiveX-Steuerelementklasse sein:

[!code-cpp[NVC_MFC_AxLoc#3](../mfc/codesnippet/cpp/mfc-activex-controls-localizing-an-activex-control_3.cpp)]

Beachten Sie, dass die untersprachen-ID in jedem Fall der Switch-Anweisung, um spezialisiertere Lokalisierung bereitzustellen überprüft werden konnte. Eine Demonstration dieser Funktion finden Sie unter den `GetResourceHandle` -Funktion in der MFC-ActiveX-Steuerelemente Beispiel [LOCALIZE](../overview/visual-cpp-samples.md).

Wenn das Steuerelement selbst in einem Container geladen wird, kann es aufrufen [COleControl:: AmbientLocaleID](../mfc/reference/colecontrol-class.md#ambientlocaleid) die Gebietsschema-ID abrufen Das Steuerelement kann dann den zurückgegebenen Gebietsschema-ID-Wert, übergeben die `GetLocalizedResourceHandle` -Funktion, die die richtige Ressourcenbibliothek lädt. Das Steuerelement sollte das resultierende Handle übergeben, sofern vorhanden, um [AfxSetResourceHandle](../mfc/reference/application-information-and-management.md#afxsetresourcehandle):

[!code-cpp[NVC_MFC_AxLoc#4](../mfc/codesnippet/cpp/mfc-activex-controls-localizing-an-activex-control_4.cpp)]

Fügen Sie das Codebeispiel oben in einer Memberfunktion des Steuerelements, z. B. eine Überschreibung der [COleControl:: OnSetClientSite](../mfc/reference/colecontrol-class.md#onsetclientsite). Darüber hinaus *M_hResDLL* muss eine Membervariable der Steuerelement-Klasse.

Sie können ähnlichen Logik verwenden, für die Lokalisierung der Eigenschaftenseite des Steuerelements. Um die Eigenschaftenseite zu lokalisieren, fügen Sie Code wie im folgenden Beispiel Ihr Eigenschaftenseite Implementierungsdatei (in einer Außerkraftsetzung der [COlePropertyPage:: OnSetPageSite](../mfc/reference/colepropertypage-class.md#onsetpagesite)):

[!code-cpp[NVC_MFC_AxLoc#5](../mfc/codesnippet/cpp/mfc-activex-controls-localizing-an-activex-control_5.cpp)]

## <a name="see-also"></a>Siehe auch

[MFC-ActiveX-Steuerelemente](../mfc/mfc-activex-controls.md)
