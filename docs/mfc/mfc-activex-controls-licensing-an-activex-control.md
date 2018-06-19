---
title: 'MFC-ActiveX-Steuerelemente: Lizenzieren eines ActiveX-Steuerelements | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
f1_keywords:
- COleObjectFactory
dev_langs:
- C++
helpviewer_keywords:
- COleObjectFactory class [MFC], licensing controls
- MFC ActiveX controls [MFC], licensing
- VerifyLicenseKey method [MFC]
- VerifyUserLicense method [MFC]
- GetLicenseKey method [MFC]
- licensing ActiveX controls
ms.assetid: cacd9e45-701a-4a1f-8f1f-b0b39f6ac303
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 725e6cf167ec01635a3072f09ecaa2f5055b1891
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33353925"
---
# <a name="mfc-activex-controls-licensing-an-activex-control"></a>MFC-ActiveX-Steuerelemente: Lizenzieren eines ActiveX-Steuerelements
Unterstützen der Lizenzierung, können ein optionales Feature von ActiveX-Steuerelemente, Sie steuern, wer verwenden oder verteilen Sie das Steuerelement ist. (Weitere Erläuterung der Lizenzierungsproblemen, finden Sie unter Lizenzierung Probleme in [Upgrading eines vorhandenen ActiveX-Steuerelements](../mfc/upgrading-an-existing-activex-control.md).)  
  
 In diesem Artikel werden die folgenden Themen erläutert:  
  
-   [Übersicht über die Lizenzierung von ActiveX-Steuerelement](#_core_overview_of_activex_control_licensing)  
  
-   [Erstellt ein lizenziertes Steuerelement](#_core_creating_a_licensed_control)  
  
-   [Unterstützen der Lizenzierung](#_core_licensing_support)  
  
-   [Anpassen der Lizenzierung von ActiveX-Steuerelement](#_core_customizing_the_licensing_of_an_activex_control)  
  
 ActiveX-Steuerelemente, die Lizenzierung implementieren ermöglicht es Ihnen als Entwickler von Steuerelementen, um zu bestimmen, wie andere Personen das ActiveX-Steuerelement verwendet werden. Geben Sie das Steuerelement "Käufer", mit dem Steuerelement und. – Lizenzvereinbarung-Datei mit der Vereinbarung, die "Käufer" das Steuerelement, aber nicht verteilen, kann die. – Lizenzvereinbarung-Datei mit einer Anwendung, die das Steuerelement verwendet. Dies verhindert, dass Benutzer diese Anwendung schreiben Sie neue Anwendungen, die das Steuerelement zu verwenden, ohne die erste Lizenzierung des Steuerelements.  
  
##  <a name="_core_overview_of_activex_control_licensing"></a> Übersicht über die Lizenzierung von ActiveX-Steuerelement  
 Um die Lizenzierung unterstützen ActiveX-Steuerelemente, die [COleObjectFactory](../mfc/reference/coleobjectfactory-class.md) -Klasse stellt eine Implementierung für mehrere Funktionen in der **IClassFactory2** Schnittstelle: **IClassFactory2 :: RequestLicKey**, **IClassFactory2:: GetLicInfo**, und **Iclassfactory2**. Wenn der Container-Anwendungsentwickler stellt eine Anforderung zum Erstellen einer Instanz des Steuerelements, einen Aufruf von `GetLicInfo` wird ausgelöst, um zu überprüfen, ob das Steuerelement. – Lizenzvereinbarung-Datei ist vorhanden. Wenn das Steuerelement lizenziert ist, kann eine Instanz des Steuerelements erstellt und im Container platziert werden. Nach Abschluss der Steuerelementcontainer-Anwendung erstellen und der Entwickler eine andere Funktion aufrufen, zurzeit `RequestLicKey`, erfolgt. Diese Funktion gibt einen Lizenzschlüssel (eine einfache Zeichenfolge) für die containeranwendung. Der zurückgegebene Schlüssel wird dann in der Anwendung eingebettet.  
  
 Die folgende Abbildung zeigt die Überprüfung der Lizenz ein ActiveX-Steuerelement, das während der Entwicklung eine Steuerelementcontainer-Anwendung verwendet wird. Wie bereits erwähnt, muss der Anwendungsentwickler Container die geeignete verfügen. – Lizenzvereinbarung-Datei, die auf dem Entwicklungscomputer zum Erstellen einer Instanz des Steuerelements installiert.  
  
 ![Lizenzierten ActiveX-Steuerelementen überprüft bei der Entwicklung](../mfc/media/vc374d1.gif "vc374d1")  
Überprüfung eines lizenzierten ActiveX-Steuerelements während der Entwicklung  
  
 Der nächste Prozess, in der folgenden Abbildung gezeigt tritt auf, wenn der Endbenutzer die containeranwendung ausgeführt wird.  
  
 Wenn die Anwendung gestartet wird, muss eine Instanz des Steuerelements erstellt werden. Der Container erreicht dies durch einen Aufruf an `CreateInstanceLic`, die eingebettete Lizenzschlüssel als Parameter übergeben. Ein Zeichenfolgenvergleich erfolgt dann zwischen den eingebetteten Lizenzschlüssel und die Kopie des Steuerelements von der Lizenzschlüssel. Wenn die Übereinstimmung erfolgreich ist, wird eine Instanz des Steuerelements erstellt und die Anwendung wird weiterhin normal ausgeführt. Beachten Sie, dass die. – Lizenzvereinbarung-Datei muss nicht auf das Steuerelement dem Computer des Benutzers vorhanden sein.  
  
 ![ActiveX-Steuerelementen, die bei der Ausführung überprüft lizenziert](../mfc/media/vc374d2.gif "vc374d2")  
Überprüfung eines lizenzierten ActiveX-Steuerelements während der Ausführung  
  
 Lizenzierung besteht aus zwei grundlegenden Komponenten: bestimmten Code in der Implementierung des Steuerelements DLL und die Lizenzdatei. Der Code besteht aus zwei (oder möglicherweise drei) Funktionsaufrufe und eine Zeichenfolge, die nachstehend als "Lizenz String", mit einem Urheberrechtshinweis. Diese Aufrufe und die Lizenzzeichenfolge befinden sich in der Implementierung des Steuerelements (. CPP)-Datei. Die Datei des License, von der ActiveX-Steuerelement-Assistent, generierte ist eine Textdatei mit einer copyright-Anweisung. Es wird mit den Namen des Projekts mit den Namen ein. – Lizenzvereinbarung-Erweiterung, z. B. Beispiel. – LIZENZVEREINBARUNG. Ein lizenziertes Steuerelement der Lizenzdatei beizufügen ggf. während der Entwurfszeit verwenden.  
  
##  <a name="_core_creating_a_licensed_control"></a> Erstellt ein lizenziertes Steuerelement  
 Wenn Sie das ActiveX-Steuerelement-Assistent zum Erstellen der Steuerelement-Framework verwenden, ist es einfach zum unterstützen der Lizenzierung enthalten. Wenn Sie angeben, dass das Steuerelement eine Laufzeitlizenz haben soll, mit dem ActiveX-Steuerelement-Assistenten der Control-Klasse, um die Lizenzierung unterstützen Code hinzugefügt. Der Code besteht aus Funktionen, die einen Schlüssel und die Lizenz für die Überprüfung der Lizenz verwenden. Diese Funktionen können auch geändert werden, um die Lizenzierung anzupassen. Weitere Informationen zur Anpassung der Lizenz finden Sie unter [Anpassen der Lizenzierung eines ActiveX-Steuerelements](#_core_customizing_the_licensing_of_an_activex_control) weiter unten in diesem Artikel.  
  
#### <a name="to-add-support-for-licensing-with-the-activex-control-wizard-when-you-create-your-control-project"></a>Hinzufügen von Unterstützung für die Lizenzierung mit dem ActiveX-Steuerelement-Assistenten bei der Erstellung auf dem Steuerelementprojekt  
  
1.  Verwenden Sie die Anweisungen im [Erstellen eines MFC-ActiveX-Steuerelements](../mfc/reference/creating-an-mfc-activex-control.md). Die **Anwendungseinstellungen** Seite des ActiveX-Steuerelement-Assistenten enthält die Option zum Erstellen des Steuerelements mit der Laufzeit-Lizenz.  
  
 Die ActiveX-Steuerelement-Assistent generiert nun ein ActiveX-Steuerelement-Framework, die grundlegende Unterstützung bei der Lizenzierung enthält. Eine ausführliche Erläuterung des Codes Lizenzierung finden Sie im nächste Thema.  
  
##  <a name="_core_licensing_support"></a> Unterstützen der Lizenzierung  
 Wenn Sie den ActiveX-Steuerelement-Assistenten verwenden, Lizenzierung Unterstützung für ein ActiveX-Steuerelement hinzufügen, fügt das ActiveX-Steuerelement-Assistent, dass Code, der deklariert und implementiert die Lizenzierung-Funktion, die Control-Header und die Implementierung Dateien hinzugefügt wird. Dieser Code besteht aus einem `VerifyUserLicense` Memberfunktion und eine `GetLicenseKey` Memberfunktion, die Überschreiben der standardmäßigen Implementierungen gefunden [COleObjectFactory](../mfc/reference/coleobjectfactory-class.md) . Diese Funktionen abrufen und überprüfen Sie die Steuerelementlizenz.  
  
> [!NOTE]
>  Eine dritte Memberfunktion `VerifyLicenseKey` ist nicht vom ActiveX-Steuerelement-Assistenten generiert, sondern können überschrieben werden, um das Verhalten der Lizenz Verifizierungsschlüssel anpassen.  
  
 Diese Memberfunktionen sind:  
  
-   [VerifyUserLicense](../mfc/reference/coleobjectfactory-class.md#verifyuserlicense)  
  
     Stellt sicher, dass das Steuerelement zur Entwurfszeit-Nutzung durch Überprüfen des Systems für das Vorhandensein der Lizenzdatei Steuerelement zulässt. Diese Funktion wird vom Framework aufgerufen, im Rahmen der Verarbeitung **IClassFactory2:: GetLicInfo** und **IClassFactory:: CreateInstanceLic**.  
  
-   [GetLicenseKey](../mfc/reference/coleobjectfactory-class.md#getlicensekey)  
  
     Fordert einen eindeutigen Schlüssel aus der DLL des Steuerelements an. Dieser Schlüssel ist in den Steuerelementcontainer-Anwendung eingebettet und höher in Verbindung mit verwendet `VerifyLicenseKey`, um eine Instanz des Steuerelements zu erstellen. Diese Funktion wird vom Framework aufgerufen, im Rahmen der Verarbeitung **IClassFactory2:: RequestLicKey**.  
  
-   [VerifyLicenseKey](../mfc/reference/coleobjectfactory-class.md#verifylicensekey)  
  
     Überprüft, ob die eingebetteten und eindeutige Schlüssel des Steuerelements identisch sind. Dadurch wird den Container zum Erstellen einer Instanz des Steuerelements für die Verwendung. Diese Funktion wird vom Framework aufgerufen, im Rahmen der Verarbeitung **Iclassfactory2** und kann überschrieben werden, um benutzerdefinierte Überprüfung des Lizenzschlüssels bereitzustellen. Die standardmäßige Implementierung führt einen Vergleich von Zeichenfolgen. Weitere Informationen finden Sie unter [Anpassen der Lizenzierung eines ActiveX-Steuerelements](#_core_customizing_the_licensing_of_an_activex_control)weiter unten in diesem Artikel.  
  
###  <a name="_core_header_file_modifications"></a> Header-Dateiänderungen  
 ActiveX-Steuerelement-Assistent fügt den folgenden Code in der Headerdatei des Steuerelements. In diesem Beispiel werden zwei Memberfunktionen der `CSampleCtrl`des Objekts `factory` deklariert werden, einen, überprüft das Vorhandensein des Steuerelements. – Lizenzvereinbarung-Datei und ein anderes, das den Lizenzschlüssel in die Anwendung, die das Steuerelement zu verwendende abruft:  
  
 [!code-cpp[NVC_MFC_AxUI#39](../mfc/codesnippet/cpp/mfc-activex-controls-licensing-an-activex-control_1.h)]  
  
###  <a name="_core_implementation_file_modifications"></a> Implementierung von Dateiänderungen  
 ActiveX-Steuerelement-Assistent setzt die folgenden beiden Anweisungen in der Implementierungsdatei des Steuerelements zum Deklarieren der Lizenz Dateiname und die Lizenzzeichenfolge:  
  
 [!code-cpp[NVC_MFC_AxUI#40](../mfc/codesnippet/cpp/mfc-activex-controls-licensing-an-activex-control_2.cpp)]  
  
> [!NOTE]
>  Wenn Sie ändern **SzLicString** in keiner Weise müssen Sie auch die erste Zeile im Steuerelement ändern. – Lizenzvereinbarung Datei- oder Lizenzierung funktioniert nicht ordnungsgemäß.  
  
 Die ActiveX-Steuerelement-Assistent stellt den folgenden Code in der Implementierungsdatei des Steuerelements zum Definieren der Steuerelementklasse `VerifyUserLicense` und `GetLicenseKey` Funktionen:  
  
 [!code-cpp[NVC_MFC_AxUI#41](../mfc/codesnippet/cpp/mfc-activex-controls-licensing-an-activex-control_3.cpp)]  
  
 Schließlich die **ActiveX-Steuerelement-Assistent** ändert das Steuerelementprojekt. IDL-Datei. Die **lizenziert** -Schlüsselwort zur Klassendeklaration Co-des Steuerelements, wie im folgenden Beispiel hinzugefügt wird:  
  
 [!code-cpp[NVC_MFC_AxUI#42](../mfc/codesnippet/cpp/mfc-activex-controls-licensing-an-activex-control_4.idl)]  
  
##  <a name="_core_customizing_the_licensing_of_an_activex_control"></a> Anpassen der Lizenzierung von ActiveX-Steuerelement  
 Da `VerifyUserLicense`, `GetLicenseKey`, und `VerifyLicenseKey` werden als deklariert virtuelle Memberfunktionen der Control-Klasse, Sie können das Verhalten des Steuerelements Lizenzierung anpassen.  
  
 Beispielsweise bieten verschiedene Ebenen der Lizenzierung für das Steuerelement durch Überschreiben der `VerifyUserLicense` oder `VerifyLicenseKey` Memberfunktionen. Innerhalb dieser Funktion können Sie festlegen, welche Eigenschaften oder Methoden, die dem Benutzer nach der Lizenz-Ebene verfügbar gemacht werden, die Sie erkannt.  
  
 Sie können auch Code zum Hinzufügen der `VerifyLicenseKey` Funktion, die eine benutzerdefinierte Methode bereitstellt, für den Benutzer, die die Erstellung steuern darüber informiert ein Fehler aufgetreten ist. Für die Instanz, in Ihrem `VerifyLicenseKey` Memberfunktion, die eine Meldung angezeigt, konnte im Feld angezeigt, die besagt, die das Steuerelement konnte nicht initialisiert werden und deren Ursachen.  
  
> [!NOTE]
>  Eine weitere Möglichkeit zum Anpassen der Überprüfung der ActiveX-Steuerelement-Lizenz ist, überprüfen Sie die Registrierungsdatenbank für eine bestimmte Registrierungsschlüssel statt `AfxVerifyLicFile`. Ein Beispiel für die standardmäßige Implementierung, finden Sie unter der [Implementierung Dateiänderungen](#_core_implementation_file_modifications) Abschnitt dieses Artikels.  
  
 Weitere Erläuterung der Lizenzierungsproblemen, finden Sie unter Lizenzierung Probleme in [Upgrading eines vorhandenen ActiveX-Steuerelements](../mfc/upgrading-an-existing-activex-control.md).  
  
## <a name="see-also"></a>Siehe auch  
 [MFC-ActiveX-Steuerelemente](../mfc/mfc-activex-controls.md)   
 [MFC-ActiveX-Steuerelement-Assistent](../mfc/reference/mfc-activex-control-wizard.md)

