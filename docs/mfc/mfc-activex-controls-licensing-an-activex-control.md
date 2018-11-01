---
title: 'MFC-ActiveX-Steuerelemente: Lizenzieren eines ActiveX-Steuerelements'
ms.date: 09/12/2018
f1_keywords:
- COleObjectFactory
helpviewer_keywords:
- COleObjectFactory class [MFC], licensing controls
- MFC ActiveX controls [MFC], licensing
- VerifyLicenseKey method [MFC]
- VerifyUserLicense method [MFC]
- GetLicenseKey method [MFC]
- licensing ActiveX controls
ms.assetid: cacd9e45-701a-4a1f-8f1f-b0b39f6ac303
ms.openlocfilehash: 4001d49da8477ab9dd481d0eb3ee02cb10e1e18b
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50465623"
---
# <a name="mfc-activex-controls-licensing-an-activex-control"></a>MFC-ActiveX-Steuerelemente: Lizenzieren eines ActiveX-Steuerelements

Lizenzierung unterstützen können ein optionales Feature von ActiveX-Steuerelemente, Sie steuern, wer kann verwenden oder verteilen das Steuerelement. (Weitere Informationen zu ermitteln, finden Sie unter Lizenzierungsprobleme im [Upgrading eines vorhandenen ActiveX-Steuerelements](../mfc/upgrading-an-existing-activex-control.md).)

>[!IMPORTANT]
> ActiveX ist eine veraltete Technologie, die nicht für Neuentwicklungen verwendet werden soll. Weitere Informationen zu moderne Technologien, die ActiveX-ablösen, finden Sie unter [ActiveX-Steuerelemente](activex-controls.md).

In diesem Artikel werden die folgenden Themen behandelt:

- [Übersicht über die Lizenzierung von ActiveX-Steuerelement](#_core_overview_of_activex_control_licensing)

- [Erstellen ein lizenziertes Steuerelement](#_core_creating_a_licensed_control)

- [Unterstützen der Lizenzierung](#_core_licensing_support)

- [Anpassen der Lizenzierung ein ActiveX-Steuerelement](#_core_customizing_the_licensing_of_an_activex_control)

ActiveX-Steuerelemente, die Lizenzierung implementieren ermöglicht es Ihnen als Entwickler von Steuerelementen, um zu bestimmen, wie andere Personen das ActiveX-Steuerelement verwendet. Sie geben der Käufer Steuerelement mit dem Steuerelement und. LIC-Datei mit der Vereinbarung an, dass der Käufer das Steuerelement, aber nicht verteilen kann die. LIC-Datei, mit einer Anwendung, die das Steuerelement verwendet. Dies verhindert, dass Benutzer der Anwendung vom Schreiben von neuen Anwendungen, die das Steuerelement, zu verwenden, ohne zuerst das Steuerelement, von Ihnen Lizenzierung.

##  <a name="_core_overview_of_activex_control_licensing"></a> Übersicht über die Lizenzierung von ActiveX-Steuerelement

Um die Lizenzierung unterstützen ActiveX-Steuerelemente, die [COleObjectFactory](../mfc/reference/coleobjectfactory-class.md) -Klasse stellt eine Implementierung für mehrere Funktionen in der `IClassFactory2` Schnittstelle: `IClassFactory2::RequestLicKey`, `IClassFactory2::GetLicInfo`, und `IClassFactory2::CreateInstanceLic`. Wenn der Container-Anwendungsentwickler stellt eine Anforderung zum Erstellen einer Instanz des Steuerelements einen Aufruf von `GetLicInfo` erfolgt, um zu überprüfen, ob das Steuerelement. LIC-Datei ist vorhanden. Wenn das Steuerelement lizenziert ist, kann eine Instanz des Steuerelements erstellt und in den Container eingefügt werden. Nach Abschluss die Container-Anwendung erstellen und der Entwickler eine andere Funktion aufrufen, dieses Mal im `RequestLicKey`, erfolgt. Diese Funktion gibt einen Lizenzschlüssel (ein einfaches Zeichen der Zeichenfolge), um die Container-Anwendung. Der zurückgegebene Schlüssel wird dann in der Anwendung eingebettet werden.

Die folgende Abbildung zeigt die lizenzüberprüfung eines ActiveX-Steuerelements, die während der Entwicklung einer Anwendung mit Containern verwendet werden. Wie bereits erwähnt, muss der Entwickler der Container-Anwendung die richtigen verfügen. LIC-Datei installiert wird, auf dem Entwicklungscomputer zum Erstellen einer Instanz des Steuerelements.

![ActiveX-Steuerelementen überprüft wird, auf die Entwicklung lizenziert](../mfc/media/vc374d1.gif "vc374d1") Überprüfung von einem lizenzierten ActiveX-Steuerelements während der Entwicklung

Der nächste Prozess, in der folgenden Abbildung gezeigten tritt auf, wenn der Endbenutzer die Container-Anwendung ausgeführt wird.

Wenn die Anwendung gestartet wird, muss eine Instanz des Steuerelements in der Regel erstellt werden. Der Container erreicht dies durch einen Aufruf an `CreateInstanceLic`, die eingebettete Lizenzschlüssel als Parameter übergeben. Ein Zeichenfolgenvergleich wird zwischen den eingebetteten Lizenzschlüssel und die Kopie des Steuerelements des Lizenzschlüssels hergestellt. Wenn die Übereinstimmung erfolgreich ist, wird eine Instanz des Steuerelements wird erstellt, und die Anwendung wird weiterhin normal ausgeführt. Beachten Sie, dass die. LIC-Datei muss nicht auf Computer des Benutzers, der das Steuerelement vorhanden sein.

![ActiveX-Steuerelementen überprüft bei der Ausführung lizenziert](../mfc/media/vc374d2.gif "vc374d2") lizenzierten ActiveX-Steuerelements während der Ausführung einer Überprüfung

Lizenzierung von ASP.NET-Serversteuerelementen besteht aus zwei grundlegenden Komponenten: spezifischen Code in der Implementierung des Steuerelements DLL und die Lizenzdatei. Der Code besteht aus zwei (oder möglicherweise drei)-Funktionsaufrufe und eine Zeichenfolge, die im folgenden als "Lizenz String", mit einem Urheberrechtshinweis bezeichnet. Diese Aufrufe und die Lizenzzeichenfolge finden Sie in der Implementierung des Steuerelements (. CPP)-Datei. Die Lizenzdatei, die von der ActiveX-Steuerelement-Assistent, generierte ist eine Textdatei mit der eine urheberrechtserklärung. Es heißt, verwenden den Namen des Projekts mit ein. LIC-Erweiterung, z. B. Beispiel. LIC. Ein lizenziertes Steuerelement muss die Lizenzdatei metaelementtyp bei Bedarf zur Entwurfszeit verwendet wird.

##  <a name="_core_creating_a_licensed_control"></a> Erstellen ein lizenziertes Steuerelement

Wenn Sie das ActiveX-Steuerelement-Assistent verwenden, um das Framework des Steuerelements zu erstellen, ist es einfach, Lizenz Unterstützung. Wenn Sie angeben, dass das Steuerelement eine Laufzeit-Lizenz erhalten sollen, mit dem ActiveX-Steuerelement-Assistenten die Control-Klasse zur Unterstützung der Lizenzierung Code hinzugefügt. Der Code besteht aus Funktionen, die eine Schlüssel und die Lizenz-Datei für die lizenzüberprüfung verwenden. Diese Funktionen können auch geändert werden, um die Lizenzierung von ASP.NET-Serversteuerelementen anzupassen. Weitere Informationen zur Anpassung der Lizenz finden Sie unter [Anpassen der Lizenzierung ein ActiveX-Steuerelement](#_core_customizing_the_licensing_of_an_activex_control) weiter unten in diesem Artikel.

#### <a name="to-add-support-for-licensing-with-the-activex-control-wizard-when-you-create-your-control-project"></a>Zum Hinzufügen von Unterstützung für die Lizenzierung mit dem ActiveX-Steuerelement-Assistenten, wenn Sie das Projekt erstellen

1. Verwenden Sie die Anweisungen in [Erstellen eines MFC-ActiveX-Steuerelements](../mfc/reference/creating-an-mfc-activex-control.md). Die **Anwendungseinstellungen** Seite des ActiveX-Steuerelement-Assistenten enthält die Option aus, um das Steuerelement mit der Run-Time-Lizenz zu erstellen.

Der ActiveX-Steuerelement-Assistent generiert jetzt einen ActiveX-Steuerelement-Framework, die grundlegende Lizenzierung Unterstützung enthält. Eine ausführliche Erläuterung des Codes Lizenzierung finden Sie im nächste Thema.

##  <a name="_core_licensing_support"></a> Unterstützen der Lizenzierung

Wenn Sie den ActiveX-Steuerelement-Assistenten verwenden, der Lizenzierung unterstützt ein ActiveX-Steuerelement hinzu, fügt der ActiveX-Steuerelement-Assistent, dass Code, der deklariert, und die lizenzierungs-Funktion implementiert die Control-Header und die Implementierung Dateien hinzugefügt wird. Dieser Code besteht aus einer `VerifyUserLicense` Memberfunktion und eine `GetLicenseKey` Memberfunktion, die die standardimplementierungen, finden Sie im außer Kraft setzen [COleObjectFactory](../mfc/reference/coleobjectfactory-class.md) . Diese Funktionen abrufen und überprüfen Sie die Steuerelementlizenz.

> [!NOTE]
>  Eine dritte Memberfunktion ist `VerifyLicenseKey` wird nicht von der ActiveX-Steuerelement-Assistent generiert, aber überschrieben werden, um das Verhalten der Lizenz Verifizierungsschlüssel anpassen.

Diese Memberfunktionen sind:

- [VerifyUserLicense](../mfc/reference/coleobjectfactory-class.md#verifyuserlicense)

   Stellt sicher, dass das Steuerelement zur Entwurfszeit Nutzung durch Überprüfen des Systems für das Vorhandensein der Lizenzdatei Steuerelement kann. Diese Funktion wird vom Framework aufgerufen, im Rahmen der Verarbeitung `IClassFactory2::GetLicInfo` und `IClassFactory::CreateInstanceLic`.

- [GetLicenseKey](../mfc/reference/coleobjectfactory-class.md#getlicensekey)

   Fordert einen eindeutigen Schlüssel aus dem DLL-Steuerelement. Dieser Schlüssel in die Container-Anwendung eingebettet ist, und wird später in Verbindung mit `VerifyLicenseKey`, um eine Instanz des Steuerelements zu erstellen. Diese Funktion wird vom Framework aufgerufen, im Rahmen der Verarbeitung `IClassFactory2::RequestLicKey`.

- [VerifyLicenseKey](../mfc/reference/coleobjectfactory-class.md#verifylicensekey)

   Überprüft, ob der eingebetteten und eindeutige Schlüssel des Steuerelements identisch sind. Dadurch wird den Container eine Instanz des Steuerelements zur eigenen Verwendung erstellen. Diese Funktion wird vom Framework aufgerufen, im Rahmen der Verarbeitung `IClassFactory2::CreateInstanceLic` und überschrieben werden, um die benutzerdefinierte Überprüfung des Lizenzschlüssels bereitstellen. Die Standardimplementierung führt einen Zeichenfolgenvergleich. Weitere Informationen finden Sie unter [Anpassen der Lizenzierung ein ActiveX-Steuerelement](#_core_customizing_the_licensing_of_an_activex_control)weiter unten in diesem Artikel.

###  <a name="_core_header_file_modifications"></a> Header-Dateiänderungen

Der ActiveX-Steuerelement-Assistent wird im folgenden Code in der Headerdatei des Steuerelements. In diesem Beispiel zwei Memberfunktionen der `CSampleCtrl`des Objekts `factory` deklariert werden, das überprüft, ob das Vorhandensein des Steuerelements. LIC-Datei und eine andere, die den Lizenzschlüssel, der in der Anwendung, die mit dem Steuerelement verwendet werden abgerufen:

[!code-cpp[NVC_MFC_AxUI#39](../mfc/codesnippet/cpp/mfc-activex-controls-licensing-an-activex-control_1.h)]

###  <a name="_core_implementation_file_modifications"></a> Implementierung von Dateiänderungen

Der ActiveX-Steuerelement-Assistent stellt die folgenden beiden Anweisungen in der Implementierungsdatei des Steuerelements zum Deklarieren der Lizenz Dateiname und die Lizenzzeichenfolge:

[!code-cpp[NVC_MFC_AxUI#40](../mfc/codesnippet/cpp/mfc-activex-controls-licensing-an-activex-control_2.cpp)]

> [!NOTE]
>  Wenn Sie ändern `szLicString` in keiner Weise verwenden, müssen Sie auch die erste Zeile im Steuerelement ändern. LIC-Datei oder zur Lizenzierung funktioniert nicht ordnungsgemäß.

Der ActiveX-Steuerelement-Assistent stellt den folgenden Code in der Implementierungsdatei des Steuerelements zum Definieren der Steuerelementklasse `VerifyUserLicense` und `GetLicenseKey` Funktionen:

[!code-cpp[NVC_MFC_AxUI#41](../mfc/codesnippet/cpp/mfc-activex-controls-licensing-an-activex-control_3.cpp)]

Zum Schluss die **ActiveX-Steuerelement-Assistent** ändert das Steuerelementprojekt. IDL-Datei. Die **lizenziert** -Schlüsselwort zur Klassendeklaration Co-des Steuerelements, wie im folgenden Beispiel hinzugefügt wird:

[!code-cpp[NVC_MFC_AxUI#42](../mfc/codesnippet/cpp/mfc-activex-controls-licensing-an-activex-control_4.idl)]

##  <a name="_core_customizing_the_licensing_of_an_activex_control"></a> Anpassen der Lizenzierung ein ActiveX-Steuerelement

Da `VerifyUserLicense`, `GetLicenseKey`, und `VerifyLicenseKey` werden als deklariert virtuelle Memberfunktionen der Steuerelement-Factoryklasse, Sie können das Verhalten des Steuerelements Lizenzierung anpassen.

Sie können beispielsweise angeben, mehrere Ebenen der Lizenzierung für das Steuerelement durch Überschreiben der `VerifyUserLicense` oder `VerifyLicenseKey` Memberfunktionen. Innerhalb dieser Funktion können Sie anpassen, welche Eigenschaften oder Methoden für den Benutzer nach der Lizenzebene verfügbar gemacht werden, die Sie erkannt.

Sie können auch Code zum Hinzufügen der `VerifyLicenseKey` -Funktion, die eine benutzerdefinierte Methode bietet für informiert den Benutzer, die steuern, Erstellung ein Fehler aufgetreten ist. Beispielsweise sind in Ihrer `VerifyLicenseKey` Feld Member-Funktion können Sie eine Meldung angezeigt, mit dem Hinweis, der das Steuerelement konnte nicht initialisiert werden und warum.

> [!NOTE]
>  Eine weitere Möglichkeit zum Anpassen der lizenzüberprüfung für ActiveX-Steuerelement wird zum Überprüfen der Registrierungsdatenbank für einen bestimmten Registrierungsschlüssel statt `AfxVerifyLicFile`. Ein Beispiel für die standardmäßige Implementierung, finden Sie unter den [Implementierung Dateiänderungen](#_core_implementation_file_modifications) Abschnitt dieses Artikels.

Weitere Informationen zu ermitteln, finden Sie unter Lizenzierungsprobleme im [Upgrading eines vorhandenen ActiveX-Steuerelements](../mfc/upgrading-an-existing-activex-control.md).

## <a name="see-also"></a>Siehe auch

[MFC-ActiveX-Steuerelemente](../mfc/mfc-activex-controls.md)<br/>
[MFC-ActiveX-Steuerelement-Assistent](../mfc/reference/mfc-activex-control-wizard.md)

