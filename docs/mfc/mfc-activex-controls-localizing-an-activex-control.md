---
title: "MFC-ActiveX-Steuerelemente: Lokalisieren eines ActiveX-Steuerelements | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "LocaleID"
  - "AfxOleRegisterTypeLib"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "LocaleID-Ambient-Eigenschaft"
  - "Lokalisierung, ActiveX-Steuerelemente"
  - "LOCALIZE-Beispiel [MFC]"
  - "MFC-ActiveX-Steuerelemente, Lokalisieren"
ms.assetid: a44b839a-c652-4ec5-b824-04392708a5f9
caps.latest.revision: 12
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 9
---
# MFC-ActiveX-Steuerelemente: Lokalisieren eines ActiveX-Steuerelements
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Dieser Artikel beschriebene Verfahren zum Suchen von ActiveX\-Steuerelement\-Schnittstellen.  
  
 Wenn Sie ein ActiveX\-Steuerelement einem internationalen Markt anpassen möchten, sollten Sie das Steuerelement suchen.  Windows unterstützt viele Sprachen zusätzlich zu Standard, einschließlich Englisch, Deutsch und Französisch Schweden.  Dies kann Probleme für das Steuerelement darstellen, wenn seine Schnittstelle nur auf Englisch ist.  
  
 Im Allgemeinen sollten ActiveX\-Steuerelemente ihr Gebietsschema auf der Umgebungsfarbe LocaleID\-Eigenschaft immer basieren.  Hierfür gibt es drei Möglichkeiten:  
  
-   Laden Sie die Ressourcen, immer bedarfsabhängig, basierend auf den aktuellen Wert der Umgebungsfarbe LocaleID\-Eigenschaft.  Die Kontrollprobe MFC ActiveX [LOKALISIEREN Sie](../top/visual-cpp-samples.md) verwendet diese Strategie.  
  
-   Laden Sie Ressourcen, wenn das erste Steuerelement, auf Grundlage der LocaleID\-Eigenschaft Umgebungspinsel als Beispiel angeführt und diese Ressourcen für alle anderen Instanzen verwendet wird.  Dieser Artikel wird diese Strategie.  
  
    > [!NOTE]
    >  Dies funktioniert nicht ordnungsgemäß in einigen Fällen, wenn die Instanzen unterschiedliche Gebietsschemas enthält.  
  
-   Verwenden Sie die **OnAmbientChanged** Benachrichtigungsfunktion, um die richtigen Ressourcen für das Gebietsschema des Containers dynamisch geladen wird.  
  
    > [!NOTE]
    >  Dies funktioniert für das Steuerelement, aber die Ablauf\-DLL nicht dynamisch aktualisiert eigene Ressourcen, wenn die LocaleID\-Eigenschaft Ambient ändert.  Außerdem verwenden Ablauf\-DLLs für ActiveX\-Steuerelemente das Threadgebietsschema, um das Gebietsschema für seine Ressourcen zu ermitteln.  
  
 Der Artikel beschreibt lokalisierende zwei Strategien.  Die erste Strategie [lokalisiert die Programmierbarkeitsschnittstelle des Steuerelements](#_core_localizing_your_control.92.s_programmability_interface) \(Namen von Eigenschaften, Methoden und Ereignisse\).  Die zweite Strategie [wird die Benutzeroberfläche des Steuerelements](#_core_localizing_the_control.92.s_user_interface), mit der Umgebungsfarbe das LocaleID\-Eigenschaft des Containers.  Eine Beispiel der Steuerlokalisierung, finden Sie die Kontrollprobe MFC ActiveX [LOKALISIEREN Sie](../top/visual-cpp-samples.md).  
  
##  <a name="_core_localizing_your_control.92.s_programmability_interface"></a> Suchen der die Programmierbarkeits\-Schnittstelle des Steuerelements  
 Wenn Sie die Programmierbarkeitsschnittstelle des Steuerelements \(die Schnittstelle verwendet von Programmierern, die Anwendungen schreiben, die das Steuerelement verwenden\), müssen Sie eine andere Version der Steueridl\-datei \(ein Skript für das Erstellen der Steuerelementtypbibliothek\) für jede Sprache erstellen suchen, den Sie zu unterstützen.  Dies ist der einzige Ort, den die Steuerelementeigenschaftennamen suchen müssen.  
  
 Wenn Sie ein lokalisiertes Steuerelement entwickeln, schließen Sie die Gebietsschema\-ID als Attribut auf der Typbibliotheksebene ein.  Wenn Sie eine Typbibliothek mit Französisch lokalisierten Eigenschaftennamen geben möchten, erstellen Sie eine Kopie des SAMPLE.IDL aufzunehmen, und rufen Sie sie SAMPLEFR.IDL auf.  Fügen Sie einem Gebietsschema\-ID\-Attribut der Datei \(die Gebietsschema\-ID für Französisch ist 0x040c\) hinzu, ähnlich dem folgenden:  
  
 [!CODE [NVC_MFC_AxLoc#1](../CodeSnippet/VS_Snippets_Cpp/NVC_MFC_AxLoc#1)]  
  
 Ändern Sie den Eigenschaftennamen in SAMPLEFR.IDL zu ihren Entsprechungen französischen, und verwenden Sie dann MKTYPLIB.EXE, um die französische Typbibliothek, SAMPLEFR.TLB zu erzeugen.  
  
 Um mehrere lokalisierte Typbibliotheken erstellen können Sie alle lokalisierten IDL\-Dateien dem Projekt hinzufügen und sie werden automatisch erstellt.  
  
#### Um einer IDL\-Datei im ActiveX\-Steuerelements fügen Sie  
  
1.  Wenn das geöffnete Steuerelementprojekt, auf das Menü **Projekt** , klicken Sie auf **Vorhandenes Element hinzufügen**.  
  
     Das Dialogfeld  **Vorhandenes Element hinzufügen** wird angezeigt.  
  
2.  Falls notwendig auf das Laufwerk und das Verzeichnis aus, das angezeigt werden soll.  
  
3.  Im Feld **Dateityp** wählen Sie **Alle Dateien \(\*.\*\)** aus.  
  
4.  Im Dateilistenfeld doppelklicken Sie auf die IDL\-Datei, die Sie im Projekt einfügen möchten.  
  
5.  Klicken Sie auf **Öffnen**, wenn Sie alle erforderlichen IDL\-Dateien hinzugefügt haben.  
  
 Da Dateien dem Projekt hinzugefügt wurden, werden sie erstellt, wenn der Rest des Projekts erstellt wird.  Die lokalisierten sind Typbibliotheken im aktuellen ActiveX\-Steuerelement\-Projektverzeichnis.  
  
 Innerhalb des Codes werden die internen Eigenschaftennamen \(normalerweise auf Englisch\) immer verwendet und werden nicht lokalisiert.  Dies schließt die Steuerdispatchzuordnung ein, funktioniert der Eigenschaftenaustausch und das Eigenschaftenseitendatenaustauschcode.  
  
 Nur Dateien möglicherweise der Typbibliothek \(.TLB\) wird in die Ressourcen der Steuerelementimplementierung \(.OCX\) gebunden.  Dies ist normalerweise die Version mit standardisierten \(in der Regel, Englisch\) Namen.  Um eine lokalisierte Version des Steuerelements sofort, das Sie das .OCX \(das Versenden müssen bereits zur Version des standardmäßigen .TLB gebunden wurde\) und das .TLB für das Gebietsschema.  Dies bedeutet, dass nur das .OCX für englische Versionen erforderlich ist, da das richtige .TLB bereits an sie gebunden wurde.  Bei anderen Gebietsschemas muss die lokalisierte Typbibliothek mit dem .OCX auch geliefert werden.  
  
 Um sicherzustellen dass Clients des Steuerelements die lokalisierte Typbibliothek finden, registrieren Sie die TLB\-Datei gebietsschemaspezifische unter dem TypeLib\-Abschnitt der Windows\-Systemregistrierung.  Der dritte Parameter \(optional\) normalerweise der [AfxOleRegisterTypeLib](../Topic/AfxOleRegisterTypeLib.md)\-Funktion wird zu diesem Zweck bereitgestellt.  Das folgende Beispiel registriert eine die französische Typbibliothek für ein ActiveX\-Steuerelement:  
  
 [!CODE [NVC_MFC_AxLoc#2](../CodeSnippet/VS_Snippets_Cpp/NVC_MFC_AxLoc#2)]  
  
 Wenn das Steuerelement registriert ist, sucht die `AfxOleRegisterTypeLib` automatisch nach der angegebenen Funktion TLB\-Datei im gleichen Verzeichnis wie das Steuerelement und registriert sie in der Windows\-Registrierungsdatenbank.  Wenn die TLB\-Datei nicht gefunden wird, hat die Funktion keine Auswirkungen.  
  
##  <a name="_core_localizing_the_control.92.s_user_interface"></a> Suchen der Benutzeroberfläche des Steuerelements  
 Um die Benutzeroberfläche eines Steuerelements zu suchen, fügen Sie BenutzerVISIBLE\-Ressourcen alles Steuerelements \(wie Eigenschaftenseiten und Fehlermeldungen\) in sprachspezifische Ressourcen\-DLLs.  Sie können die LocaleID\-Eigenschaft Umgebungspinsel das des Containers dann verwenden, um die entsprechende DLL für das Gebietsschema des Benutzers auszuwählen.  
  
 Im folgenden Codebeispiel wird ein Verfahren, um die Ressourcen\-DLL für ein bestimmtes Gebietsschema zu finden und zu laden.  Diese Memberfunktion, `GetLocalizedResourceHandle` für dieses Beispiel, kann eine Memberfunktion die ActiveX\-Steuerelementklasse sein:  
  
 [!CODE [NVC_MFC_AxLoc#3](../CodeSnippet/VS_Snippets_Cpp/NVC_MFC_AxLoc#3)]  
  
 Beachten Sie, dass der Sprachvarianten\-ID eingecheckt werden konnte jeder Kleinschreibung der switch\-Anweisung, um spezielle Lokalisierung bereitzustellen.  Eine Beispiel dieser Funktion, finden Sie die Funktion `GetResourceHandle` in der Kontrollprobe MFC ActiveX [LOKALISIEREN Sie](../top/visual-cpp-samples.md).  
  
 Wenn das Steuerelement zuerst sicher in einem Container geladen wird, kann es [COleControl::AmbientLocaleID](../Topic/COleControl::AmbientLocaleID.md) aufrufen, um die Gebietsschema\-ID abzurufen  Das Steuerelement kann den zurückgegebenen Gebietsschema\-ID\-Wert zur Funktion dann `GetLocalizedResourceHandle` übergeben, die die richtige Ressourcenbibliothek lädt.  Das Steuerelement muss das resultierende Handle ggf. an [AfxSetResourceHandle](../Topic/AfxSetResourceHandle.md) übergeben:  
  
 [!CODE [NVC_MFC_AxLoc#4](../CodeSnippet/VS_Snippets_Cpp/NVC_MFC_AxLoc#4)]  
  
 Platzieren Sie das obige Codebeispiel in eine Memberfunktion des Steuerelements, z eine Überschreibung von [COleControl::OnSetClientSite](../Topic/COleControl::OnSetClientSite.md).  Außerdem sollte `m_hResDLL` eine Membervariable der Steuerelementklasse sein.  
  
 Sie können ähnliche Logik zum Suchen der Eigenschaftenseite eines Steuerelements verwenden.  Um die Eigenschaftenseite zu lokalisieren, fügen Sie den Code hinzu, der dem folgenden Beispiel der Implementierungsdatei der Eigenschaftenseite entspricht \(in einer Überschreibung von [COlePropertyPage::OnSetPageSite](../Topic/COlePropertyPage::OnSetPageSite.md)\):  
  
 [!CODE [NVC_MFC_AxLoc#5](../CodeSnippet/VS_Snippets_Cpp/NVC_MFC_AxLoc#5)]  
  
## Siehe auch  
 [MFC\-ActiveX\-Steuerelemente](../mfc/mfc-activex-controls.md)