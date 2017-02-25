---
title: "MFC-ActiveX-Steuerelemente: Lizenzieren eines ActiveX-Steuerelements | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "COleObjectFactory"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "COleObjectFactory-Klasse, Lizenzierte Steuerelemente"
  - "GetLicenseKey-Methode"
  - "Lizenzieren von ActiveX-Steuerelementen"
  - "MFC-ActiveX-Steuerelemente, Lizenzieren"
  - "VerifyLicenseKey-Methode"
  - "VerifyUserLicense-Methode"
ms.assetid: cacd9e45-701a-4a1f-8f1f-b0b39f6ac303
caps.latest.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 6
---
# MFC-ActiveX-Steuerelemente: Lizenzieren eines ActiveX-Steuerelements
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Unterstützung lizenzierend, kann eine optionale Funktion von ActiveX\-Steuerelementen, Sie das Steuerelement, das ist, das Steuerelement zu verwenden oder zu verteilen. \(Weitere Informationen Lizenzierungsprobleme, finden Sie Lizenzierungs\-Probleme in [Aktualisieren eines vorhandenen ActiveX\-Steuerelements](../mfc/upgrading-an-existing-activex-control.md).\)  
  
 In diesem Artikel werden die folgenden Themen:  
  
-   [Übersicht des ActiveX\-Steuerelement\-Lizenzierens](#_core_overview_of_activex_control_licensing)  
  
-   [Erstellen eines lizenzierten Steuerelements](#_core_creating_a_licensed_control)  
  
-   [Lizenzieren der Unterstützung](#_core_licensing_support)  
  
-   [Anpassen der Lizenzierung eines ActiveX\-Steuerelements](#_core_customizing_the_licensing_of_an_activex_control)  
  
 ActiveX\-Steuerelemente, die Lizenzierung implementieren, können Sie, als Entwickler von Steuerelementen, um zu bestimmen wie andere Personen das ActiveX\-Steuerelement verwenden.  Sie stellen den Steuerkäufer mit dem Steuerelement und der LIC\-Datei, mit dem Vertrag, dass der das Steuerelement Käufer verteilt, jedoch nicht der LIC\-Datei, mit einer Anwendung, die das Steuerelement verwendet.  So wird verhindert Benutzer dieser Anwendung am Schreiben neue Anwendungen, die das Steuerelement verwenden, ohne zuerst Lizenzierung des Steuerelements von Ihnen.  
  
##  <a name="_core_overview_of_activex_control_licensing"></a> Übersicht des ActiveX\-Steuerelement\-Lizenzierens  
 Um Lizenzierungsunterstützung für ActiveX\-Steuerelemente zu unterstützen, stellt die [COleObjectFactory](../mfc/reference/coleobjectfactory-class.md)\-Klasse eine Implementierung für einige Funktionen in der Schnittstelle **IClassFactory2** bereit: **IClassFactory2::RequestLicKey**, **IClassFactory2::GetLicInfo** und **IClassFactory2::CreateInstanceLic**.  Wenn der Containeranwendungsentwickler einen anfordernden, eine Instanz des Steuerelements erstellt, wird ein Aufruf von `GetLicInfo` ausgeführt, um sicherzustellen, dass die Steuerlic\-datei vorhanden ist.  Wenn das Steuerelement lizenziert wird, kann eine Instanz des Steuerelements in den Container erstellt und gespeichert werden.  Nachdem sich der Entwickler beendet, die Containeranwendung erstellen, wird ein anderer Funktionsaufruf, dieses Mal zu `RequestLicKey`, ausgeführt.  Diese Funktion gibt einen Lizenzschlüssel \(eine einfache Zeichenfolge\) der Containeranwendung zurück.  Die zurückgegebene Schlüssel wird dann in der Anwendung eingebettet.  
  
 Die folgende Abbildung zeigt die Lizenzüberprüfung eines ActiveX\-Steuerelements, das während der Entwicklung einer Containeranwendung verwendet wird.  Wie zuvor erwähnt, muss der Containeranwendungsentwickler die richtige LIC\-Datei haben, die auf dem Entwicklungscomputer installiert ist, um eine Instanz des Steuerelements erstellen.  
  
 ![Lizenz bei der Entwicklung von ActiveX&#45;Steuerelementen überprüft](../mfc/media/vc374d1.png "vc374D1")  
Überprüfung eines lizenzierten ActiveX\-Steuerelements während der Entwicklung  
  
 Der folgende Prozess, die in der folgenden Abbildung, tritt auf, wenn der Endbenutzer die Containeranwendung ausführt.  
  
 Wenn die Anwendung gestartet wird, eine Instanz der Steuernormalerweise Anforderungen erstellt.  Der Container erreicht dies, indem ein Aufruf von `CreateInstanceLic` macht und den eingebetteten Lizenzschlüssel als Parameter übergibt.  Ein Zeichenfolgenvergleich wird dann der eigene Kopie zwischen dem eingebetteten Lizenzschlüssel und des Steuerelements des Lizenzschlüssels verglichen.  Wenn die Übereinstimmung erfolgreich, wird eine Instanz des Steuerelements erstellt und die Anwendung weiter, um normalerweise ausführen.  Beachten Sie, dass die LIC\-Datei nicht, muss auf dem Computer des Steuerbenutzers vorhanden sein.  
  
 ![Lizenz bei der Ausführung von ActiveX&#45;Steuerelementen überprüft](../mfc/media/vc374d2.png "vc374D2")  
Überprüfung eines lizenzierten ActiveX\-Steuerelements während der Ausführung  
  
 Steuerlizenzierung besteht aus zwei grundlegenden Komponenten: spezieller Code in der Steuerelementimplementierung DLL und der Lizenzdatei.  Der Code wird von zwei \(oder möglicherweise drei\) Funktionsaufrufen und aus einer Zeichenfolge zusammen, anschließend wird als "Lizenzzeichenfolge" und enthält einen Copyrighthinweis.  Diese Aufrufe und die Lizenzzeichenfolge werden in der Steuerelementimplementierung \(.CPP\) gefunden.  Die Lizenzdatei, generiert der ActiveX\-Steuerelement\-Assistenten, ist eine Textdatei mit einer Urheberrechtserklärung.  Sie wird mithilfe des Projektnamens mit einer .LIC\-Erweiterung, beispielsweise SAMPLE.LIC benannt.  Ein lizenziertes Steuerelement muss der Lizenzdatei begleitet werden, wenn Entwurfszeitverwendung benötigt wird.  
  
##  <a name="_core_creating_a_licensed_control"></a> Erstellen eines lizenzierten Steuerelements  
 Wenn Sie den ActiveX\-Steuerelement\-Assistenten verwenden, um das Steuerframework zu erstellen, ist es einfach, Lizenzierungsunterstützung einzuschließen.  Wenn Sie angeben, dass das Steuerelement eine Ablauflizenz haben sollte, fügt der ActiveX\-Steuerelement\-Assistent Code der Steuerelementklasse Stützlizenzierung hinzu.  Der Code besteht aus Funktionen, die einen Schlüssel und eine für Lizenzüberprüfung Lizenzdatei verwenden.  Diese Features können auch geändert werden, um die Steuerlizenzierung anzupassen.  Weitere Informationen über Lizenzanpassung, finden Sie unter [Anpassen der Lizenzierung eines ActiveX\-Steuerelements](#_core_customizing_the_licensing_of_an_activex_control) weiter unten in diesem Artikel.  
  
#### So fügen Sie Unterstützung zum Lizenzieren mit dem ActiveX\-Steuerelement\-Assistenten hinzufügen, wenn Sie das Steuerelementprojekt erstellen  
  
1.  Verwenden Sie die Anweisungen in [Erstellen eines MFC\-ActiveX\-Steuerelements](../mfc/reference/creating-an-mfc-activex-control.md).  Die Seite **Anwendungseinstellungen** des ActiveX\-Steuerelement\-Assistenten enthält die Option, das Steuerelement mit der Ablauflizenz zu erstellen.  
  
 Der ActiveX\-Steuerelement\-Assistent generiert jetzt ein ActiveX\-Steuerelement\-Framework, das grundlegende Lizenzierungsunterstützung enthält.  Eine ausführliche Erläuterung des Lizenzierungscodes, finden Sie im nächsten Thema.  
  
##  <a name="_core_licensing_support"></a> Lizenzieren der Unterstützung  
 Wenn Sie den ActiveX\-Steuerelement\-Assistenten verwenden, um Lizenzierungsunterstützung einem ActiveX\-Steuerelement hinzufügen, fügt der ActiveX\-Steuerelement\-Assistent Code hinzu, der deklariert und implementiert die Lizenzierungsfunktion wird der Steuerkopfzeile und \-Implementierungsdateien hinzugefügt.  Dieser Code wird von einer `VerifyUserLicense`\-Memberfunktion und einer `GetLicenseKey`\-Memberfunktion zusammen, die die Standardimplementierungen überschreiben, die in [COleObjectFactory](../mfc/reference/coleobjectfactory-class.md).  Diese rufen Funktionen ab und überprüfen die Steuerlizenz.  
  
> [!NOTE]
>  Eine dritte Memberfunktion, `VerifyLicenseKey` wird nicht vom ActiveX\-Steuerelement\-Assistenten generiert, jedoch kann überschrieben werden, um das Lizenzschlüsselüberprüfungsverhalten anzupassen.  
  
 Diese Memberfunktionen sind:  
  
-   [VerifyUserLicense](../Topic/COleObjectFactory::VerifyUserLicense.md)  
  
     Überprüft, ob das Steuerelement Entwurfszeitverwendung zulässt, indem das System das Vorhandensein der Steuerlizenzdatei überprüft.  Diese Funktion wird durch das Framework als Teil der Verarbeitung aus **IClassFactory2::GetLicInfo** und **IClassFactory::CreateInstanceLic** aufgerufen.  
  
-   [GetLicenseKey](../Topic/COleObjectFactory::GetLicenseKey.md)  
  
     Fordert einen eindeutigen Schlüssel aus der Steuer\-DLL.  Dieser Schlüssel wird in der Containeranwendung eingebettet und später verwendet, in Verbindung mit `VerifyLicenseKey`, um eine Instanz des Steuerelements erstellen.  Diese Funktion wird durch das Framework als Teil der Verarbeitung von **IClassFactory2::RequestLicKey** aufgerufen.  
  
-   [VerifyLicenseKey](../Topic/COleObjectFactory::VerifyLicenseKey.md)  
  
     Überprüft, ob die eingebettete Schlüssel und der eindeutige Schlüssel des Steuerelements übereinstimmen.  Dies ermöglicht dem Container, um eine Instanz des Steuerelements für seine Verwendung zu erstellen.  Diese Funktion wird durch das Framework als Teil der Verarbeitung von **IClassFactory2::CreateInstanceLic** genannt und kann überschrieben werden, um benutzerdefinierte Überprüfung des Lizenzschlüssels bereitzustellen.  Die Standardimplementierung vergleicht den aus.  Weitere Informationen finden Sie unter [Anpassen der Lizenzierung eines ActiveX\-Steuerelements](#_core_customizing_the_licensing_of_an_activex_control), später in diesem Artikel.  
  
###  <a name="_core_header_file_modifications"></a> Headerdatei\-Änderungen  
 Der ActiveX\-Steuerelement\-Assistent platziert den folgenden Code in der Steuerheaderdatei.  In diesem Beispiel werden zwei Memberfunktionen bereit von `CSampleCtrl`\-Objekt `factory`, eines, das Vorhandensein der Steuerlic\-datei überprüft und anders deklariert, das den abruft in der Anwendung verwendete Lizenzschlüssel, die das Steuerelement enthält:  
  
 [!CODE [NVC_MFC_AxUI#39](../CodeSnippet/VS_Snippets_Cpp/NVC_MFC_AxUI#39)]  
  
###  <a name="_core_implementation_file_modifications"></a> Implementierungsdatei\-Änderungen  
 Der ActiveX\-Steuerelement\-Assistent platziert die folgenden zwei Anweisungen in der Steuerimplementierungsdatei, um den Lizenzdateinamen zu deklarieren und Zeichenfolge zu Lizenzierung:  
  
 [!CODE [NVC_MFC_AxUI#40](../CodeSnippet/VS_Snippets_Cpp/NVC_MFC_AxUI#40)]  
  
> [!NOTE]
>  Wenn Sie **szLicString** in beliebig ändern, müssen Sie die erste Zeile in der Steuerlic\-datei auch ändern, oder Lizenzierung funktioniert nicht ordnungsgemäß.  
  
 Der ActiveX\-Steuerelement\-Assistent platziert den folgenden Code in der Steuerimplementierungsdatei, um die `VerifyUserLicense` und `GetLicenseKey`\-Funktionen der Steuerelementklassen zu definieren:  
  
 [!CODE [NVC_MFC_AxUI#41](../CodeSnippet/VS_Snippets_Cpp/NVC_MFC_AxUI#41)]  
  
 Schließlich ändert **ActiveX\-Steuerelement\-Assistent** die Steuerelementprojektidl\-datei.  Das **licensed**\-Schlüsselwort wird zur Co\-Klassen\-Deklaration des Steuerelements, wie im folgenden Beispiel hinzugefügt:  
  
 [!CODE [NVC_MFC_AxUI#42](../CodeSnippet/VS_Snippets_Cpp/NVC_MFC_AxUI#42)]  
  
##  <a name="_core_customizing_the_licensing_of_an_activex_control"></a> Anpassen der Lizenzierung eines ActiveX\-Steuerelements  
 Da `VerifyUserLicense`, `GetLicenseKey` und `VerifyLicenseKey` als virtuelle Memberfunktionen der Control Factory\-Klasse deklariert wurden, können Sie das Lizenzierungsverhalten des Steuerelements anpassen.  
  
 Beispielsweise können Sie mehrere Ebenen der Lizenzierung für das Steuerelement vom Überschreiben der `VerifyUserLicense` oder `VerifyLicenseKey`\-Memberfunktionen bereitstellen.  Innerhalb dieser Funktion können Sie anpassen, welche Eigenschaften oder Methoden zum Benutzer entsprechend der Lizenzebene verfügbar gemacht werden, die Sie erkannten.  
  
 Sie können Code der `VerifyLicenseKey`\-Funktion auch hinzufügen, die eine benutzerdefinierte Methode zum Informieren des Benutzers bereitstellt, die Erstellung ist fehlgeschlagen steuern.  Beispielsweise in der `VerifyLicenseKey`\-Memberfunktion können Sie ein Meldungsfeld anzeigen, dass das Steuerelement initialisiert werden konnte und warum.  
  
> [!NOTE]
>  Eine andere Möglichkeit, ActiveX\-Steuerelement\-Lizenzüberprüfung ist, anzupassen die Registrierungsdatenbank nach einem bestimmten Registrierungsschlüssel zu überprüfen, anstatt, `AfxVerifyLicFile` aufzurufen.  Ein Beispiel aus der Standardimplementierung, finden Sie im Abschnitt [Implementierungsdatei\-Änderungen](#_core_implementation_file_modifications) dieses Artikels.  
  
 Weitere Informationen Lizenzierungsprobleme, finden Sie Lizenzierungs\-Probleme in [Aktualisieren eines vorhandenen ActiveX\-Steuerelements](../mfc/upgrading-an-existing-activex-control.md).  
  
## Siehe auch  
 [MFC\-ActiveX\-Steuerelemente](../mfc/mfc-activex-controls.md)   
 [MFC\-ActiveX\-Steuerelement\-Assistent](../mfc/reference/mfc-activex-control-wizard.md)