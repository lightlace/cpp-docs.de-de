---
title: "TN057: Lokalisierung von MFC-Komponenten | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vc.mfc.components"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Komponenten [MFC], Lokalisieren"
  - "DLLs [C++], Lokalisieren von MFC"
  - "Lokalisierung [C++], MFC-Komponenten"
  - "Lokalisierung [C++], MFC-Ressourcen"
  - "Lokalisierung [C++], Ressourcen"
  - "MFC-DLLs [C++], Lokalisieren"
  - "Ressourcen [MFC], Lokalisierung"
  - "TN057"
ms.assetid: 5376d329-bd45-41bd-97f5-3d895a9a0af5
caps.latest.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 6
---
# TN057: Lokalisierung von MFC-Komponenten
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

> [!NOTE]
>  Der folgende technische Hinweis wurde seit dem ersten Erscheinen in der Onlinedokumentation nicht aktualisiert.  Daher können einige Verfahren und Themen veraltet oder falsch sein.  Um aktuelle Informationen zu erhalten, wird empfohlen, das gewünschte Thema im Index der Onlinedokumentation zu suchen.  
  
 Dieser Hinweis beschreibt einige der Entwürfe und der Prozeduren, die Sie verwenden können, um die Komponente zu suchen, wenn eine Anwendung oder ein OLE\-Steuerelement oder DLL, die MFC verwendet.  
  
## Übersicht  
 Es ist tatsächlich zwei Probleme, um das Problem zu beheben, wenn eine Komponente sucht, die MFC verwendet.  Zuerst müssen Sie eigene Ressourcen suchen \- Zeichenfolgen, Dialogfelder und anderen Ressourcen, die an die Komponente bestimmt sind.  Die meisten Komponenten, die mit MFC auch erstellt werden, enthalten und verwenden verschiedene Ressourcen, die von MFC definiert werden.  Sie müssen MFC\-Ressourcen auch lokalisierte bereitstellen.  Glücklicherweise werden einige Sprachen bereits von MFC selbst bereitgestellt.  
  
 Außerdem sollte die Komponente vorbereitet werden, in der Zielumgebung \(europäische oder DBCS\-aktivierte Umgebung\) ausgeführt werden.  In den meisten Fällen ist dieses von der Anwendung ab, die Zeichen den hohen Bit behandelt, das ordnungsgemäß festgelegt ist und Zeichenfolgen mit doppelten Bytezeichen, die behandelt.  MFC ist standardmäßig für beide Umgebung, so können, dass es möglich ist, eine einzelne weltweite Binärdatei zu haben, die auf allen Zielplattformen nur den verschiedenen Ressourcen verwendet wird, die an der Setup verbunden werden.  
  
## Suchen der Ressourcen der Komponente  
 Das Lokalisieren Ihrer Anwendung oder DLL sollte die Ressourcen, mit Ressourcen einfach zu ersetzen einbeziehen, die die Zielsprache übereinstimmen.  Für eigene Ressourcen ist dies relativ einfach: bearbeiten Sie die Ressourcen im Ressourcen\-Editor und erstellen Sie die Anwendung.  Wenn der Code korrekt geschrieben ist, existiert keine Zeichenfolgen, oder Text zu, Sie werden in die C\+\+\-Quellcode\-all\-Lokalisierung lokalisieren möchten, können erreichen, indem einfach Ressourcen geändert wird.  Tatsächlich können Sie die Komponente so implementieren, dass eine lokalisierte Version so bereitstellen nicht einmal einen Build des ursprünglichen Codes enthält.  Dies ist jedoch komplexer, muss es aus und ist der Mechanismus, der für MFC selbst ausgewählt ist.  Es ist auch möglich, eine Anwendung zu suchen, indem Sie direkt die EXE\- oder DLL\-Datei in den Ressourcen\-Editor lädt und Ressourcen.  Wenn möglich, erfordert aber reapplication dieser Änderungen an, wenn Sie eine neue Version der Anwendung erstellen.  
  
 Eine Möglichkeit zu vermeiden, die, alle Ressourcen in einer separaten DLL zu suchen, ist manchmal als angezeigt.  Diese DLL wird dann dynamisch zur Laufzeit geladen und die Ressourcen werden von dieser DLL statt des Hauptmoduls für den gesamten Code geladen.  MFC unterstützt direkt diesem Ansatz.  Nehmen Sie eine Anwendung als MYAPP.EXE bezeichnet; es konnte alle Ressourcen haben in einer DLL, die MYRES.DLL aufgerufen wurde.  `InitInstance` In der Anwendung würden sie Folgendes ausführen, um die DLL zu laden und zu MFC, dass Ressourcen von diesem Ort zu laden:  
  
```  
CMyApp::InitInstance()  
{  
   // one of the first things in the init code  
   HINSTANCE hInst = LoadLibrary("myres.dll");  
   if (hInst != NULL)  
      AfxSetResourceHandle(hInst);  
  
   // other initialization code would follow  
   .  
   .  
   .  
}  
```  
  
 Ab MFC Ressourcen lädt dann von dieser DLL statt von myapp.exe.  Alle Ressourcen müssen in dieser DLL vorhanden jedoch sein; MFC wird die Instanz der Anwendung nicht auf der Suche nach einer bestimmten Ressource.  Diese Technik wird genauso gute auf reguläre DLL sowie OLE\-Steuerelemente zu.  Das Setupprogramm wird die entsprechende Version von MYRES.DLL kopieren, je nach Ressourcengebietsschema der Benutzer möchte.  
  
 Es ist relativ einfach, eine Ressource nur zu erstellen.  Sie erstellen ein DLL\-Projekt, fügen die RC\-Datei hinzu und fügen die erforderlichen Ressourcen hinzu.  Wenn Sie ein vorhandenes Projekt, das diese Vorgehensweise nicht verwendet, können die Ressourcen dieses Projekt.  Nachdem Sie der Ressourcendatei dem Projekt hinzugefügt haben, sind Sie fast bereit, das Projekt zu erstellen.  Der einzige Aufgabe, die Sie unternehmen müssen, wird die Linkeroptionen, **\/NOENTRY** einzuschließen festgelegt.  Dies weist den Linker mit, dass die DLL keinen Einstiegspunkt hat \- da sie keinerlei Code hat, hat sie keinen Einstiegspunkt.  
  
> [!NOTE]
>  Der Ressourcen\-Editor in Visual C\+\+ 4.0 und höhere Stützmehrere Sprachen pro RC\-Datei.  Dies kann sehr vereinfachen, die Lokalisierung in einem Projekt zu verwalten.  Die Ressourcen für jede Sprache sind nach Präprozessordirektive gesteuert, die durch den Ressourcen\-Editor generiert werden.  
  
## Verwenden der bereitgestellten MFC lokalisierten Ressourcen  
 Eine MFC\-Anwendung, dass Sie zwei Punkte Wiederverwendung von MFC erstellen: Code und Ressourcen.  Das heißt, verfügt MFC verschiedene Fehlermeldungen, integrierte Dialogfelder und andere Ressourcen, die von MFC\-Klassen verwendet werden.  Um die Anwendung vollständig zu suchen, müssen Sie nicht nur die Ressourcen der Anwendung, aber auch die Ressourcen suchen die direkt von MFC stammen.  MFC bietet verschiedene Sprachressourcendateien automatisch, sodass, wenn auf die Sprache, die Sie abzielen, eine Unterstützung der Sprachen MFC bereits, müssen Sie nur sicher ist, dass Sie die lokalisierten Ressourcen verwenden.  
  
 Ab diesem Schreiben unterstützt MFC Chinesisch, Deutsch, Spanisch, Französisch, Italienisch, Japanisch und Koreanisch.  Die Dateien, die die lokalisierten Versionen enthalten, befinden sich in den Verzeichnissen MFC\\INCLUDE\\L.\* \("L" steht für Lokalisierung\).  Die deutschen Dateien befinden sich z. . in MFC\\INCLUDE\\L.DEU.  Um die Anwendung zu verursachen diese RC\-Dateien statt Dateien verwendet in MFC \\ im INCLUDE, fügen Sie `/IC:\PROGRAM FILES\MICROSOFT VISUAL STUDIO .NET 2003\VC7\MFC\INCLUDE\L.DEU` der RC\-Befehlszeile hinzu \(Dies ist nur ein Beispiel; Sie würden das Gebietsschema der Auswahl des Verzeichnisses sowie ersetzen müssen, in dem Sie Visual C\+\+ installiert\).  
  
 Die vorangehenden Anweisungen arbeiten wenn die Anwendungslinks statisch mit MFC.  Der gängigste Reguläre dynamisch \(da der Anwendungs\-Assistenten\-Standard ist\).  In diesem Szenario nicht, nur wird Code dynamisch verknüpft \- sodass die Ressourcen.  Daher können Sie die Ressourcen in der Anwendung finden, die MFC\-Implementierungsressourcen werden weiterhin vom MFC7x.DLL \(oder einer höheren Version\) oder von MFC7xLOC.DLL geladen, sofern vorhanden.  Sie können zu diesem von zwei verschiedenen Winkeln nähern.  
  
 Komplexere der Ansatz, ein von lokalisierten MFC7xLOC.DLLs \(wie MFC7xDEU ist, für Deutsch, MFC7xESP.DLL für Spanisch, z.\) oder eine höhere Version zu versenden und das entsprechende MFC7xLOC.DLL im Systemverzeichnis installiert, wenn der Benutzer die Anwendung installiert.  Dies kann für den Entwickler sehr komplex sein und der Endbenutzer und als solche wird nicht empfohlen.  Siehe [Technischer Hinweis 56](../mfc/tn056-installation-of-localized-mfc-components.md) weitere Informationen zu diesem Verfahren und seine Vorsicht.  
  
 Die einfachste und sicherste Ansatz ist, die lokalisierte MFC\-Ressourcen in Ihrer Anwendung oder in DLL selbst \(oder ihre Satelliten\-DLLs, wenn Sie ein verwenden\) einzuschließen.  Dies vermeidet die Probleme von MFC7xLOC.DLL ordnungsgemäß installieren.  Hierzu, befolgen Sie die gleichen Anweisungen für den statischen Fall, der oben angegeben ist \(die RC\-Befehlszeile ordnungsgemäß festzulegen um auf die lokalisierten Ressourcen verweisen\), außer dass Sie müssen `/D_AFXDLL` auch entfernen definieren das vom Anwendungs\-Assistenten hinzugefügt wurde.  Wenn `/D_AFXDLL` definiert wurde, definieren AFXRES.H \(und die anderen Dateien MFC RC\) eigentlich keine Ressourcen \(da sie aus MFC\-DLLs stattdessen gezogen werden\).  
  
## Siehe auch  
 [Technische Hinweise – nach Nummern geordnet](../mfc/technical-notes-by-number.md)   
 [Technische Hinweise – nach Kategorien geordnet](../mfc/technical-notes-by-category.md)