---
title: "WSADATA-Struktur | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "WSADATA"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "WSADATA-Struktur"
ms.assetid: 80cc60e5-f9ae-4290-8ed5-07003136627d
caps.latest.revision: 11
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 12
---
# WSADATA-Struktur
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Die Struktur `WSADATA` wird den Schaufenster Socket\-Initialisierungsinformationen verwendet, die bei einem Aufruf der globalen Funktion `AfxSocketInit` zurückgegeben werden.  
  
## Syntax  
  
```  
  
      struct WSAData {  
   WORD wVersion;  
   WORD wHighVersion;  
   char szDescription[WSADESCRIPTION_LEN+1];  
   char szSystemStatus[WSASYSSTATUS_LEN+1];  
   unsigned short iMaxSockets;  
   unsigned short iMaxUdpDg;  
   char FAR * lpVendorInfo;  
};  
```  
  
#### Parameter  
 *wVersion*  
 Die Version der Windows Socket\-Spezifikation, dass Windows Sockets DLL den Aufrufer erwartet zu verwenden.  
  
 *wHighVersion*  
 Die höchste Version der Windows Socket\-Spezifikation, die diese DLL unterstützen kann \(auch wie oben codiert\).  Normalerweise entspricht dies dem wie **wVersion**.  
  
 *szDescription*  
 Ein mit Null endendes ASCII reiht in, das die Windows Sockets DLL eine Beschreibung der Windows Socket\-Implementierung kopiert, einschließlich Anbieteridentifikation auf.  Der Text \(bis 256 Buchstaben long\) können alle Zeichen, Anbieter jedoch enthalten werden gewarnt vor dem Einbinden von Steuerelement\- und Formatierungszeichen: die wahrscheinlichste Verwendung, dass eine Anwendung dieses zu wird, ist, sie \(möglicherweise abgeschnitten\) in einer Statusmeldung anzuzeigen.  
  
 *szSystemStatus*  
 Ein mit Null endendes ASCII reiht auf, das die Windows Sockets DLL relevanten Status oder Konfigurationsinformationen kopiert.  Die Windows Sockets DLL sollte dieses Feld verwenden, wenn die Informationen möglicherweise den Benutzer oder die Supportmitarbeiter nützlich sind; darf nicht als eine Erweiterung des Felds **szDescription** betrachtet werden.  
  
 *iMaxSockets*  
 Die maximale Anzahl Sockets, die ein einzelner Prozess geöffnet werden kann.  Eine Windows Socket\-Implementierung kann einen globalen Pool von Sockets für Zuordnungs\- zu jedem Prozess bereitgestellt; abwechselnd kann sie pro Prozess für Sockets zuordnen Ressourcen.  Die Zahl kann zufrieden stellend ausgeführt wird spiegeln die Methode, in der die Windows Sockets DLL oder die Netzwerk\-Software konfiguriert wurden.  Anwendungsentwickler können diese Zahl als grobes Angabe verwenden, ob die Socket\-Implementierung Windows mithilfe verwendbar ist.  Beispielsweise überprüft u ein X Windows\-Server **iMaxSockets**, wenn Sie zum ersten Mal gestartet werden: wenn sie weniger als 8 ist, wird die Anwendung eine Fehlermeldung anzeigen, die den Benutzer angewiesen, um die Netzwerk\-Software neu. \(Dies ist eine Situation, in der der **szSystemStatus** Text verwendet wird\). Natürlich gibt es keine Garantie dafür, dass eine bestimmte Anwendung **iMaxSockets** Sockets tatsächlich verknüpfen kann, wie andere Windows Socket\-Anwendungen in Verwendung bereitstellen kann.  
  
 *iMaxUdpDg*  
 Die Größe in Bytes der größten User Datagram\-Protokoll\- \(UDP\)\- Datagramms, das von einer Windows Socket\-Anwendung werden gesendet oder empfangen werden kann.  Wenn die Implementierung keine Begrenzung auferlegt, **iMaxUdpDg** ist null.  In vielen Implementierungen von Berkeley\-Sockets, gibt es eine implizite Grenze von 8192 Bytes bei UDP\-Datagrammen \(die ggf. fragmentiert werden\).  Eine Windows Socket\-Implementierung kann eine abfragebasierte Grenze verlangen zum Beispiel in der Zuordnung aus Fragmentwiederversammlungspuffern.  Der minimale Wert **iMaxUdpDg** für eine kompatible Windows Socket\-Implementierung ist 512.  Beachten Sie dass unabhängig davon den Wert von **iMaxUdpDg**, es ist unratsam zu versuchen, ein Übertragungsdatagramm, das größer, als die maximale Übertragungseinheit \(MTU\) für das Netzwerk zu senden. Die \(Windows Sockets API stellt keinen Mechanismus, um das MTU aufzufinden, sie muss keine weniger als 512 Bytes bestehen\).  
  
 *lpVendorInfo*  
 Ein weiter Zeiger auf eine anbieterspezifischen Datenstruktur.  Die Definition dieser Struktur \(wenn Sie angegeben werden\), ist im Rahmen der Windows Socket\-Spezifikation.  
  
> [!NOTE]
>  In MFC wird die Struktur `WSADATA` durch die `AfxSocketInit`\-Funktion zurückgegeben, die Sie in der `InitInstance`\-Funktion aufrufen.  Sie können die Struktur abrufen und im Programm speichern, wenn Sie Informationen aus ihr später verwenden müssen.  
  
## Anforderungen  
 **Header:** winsock2.h  
  
## Siehe auch  
 [Strukturen, Stile, Rückrufe und Meldungszuordnungen](../../mfc/reference/structures-styles-callbacks-and-message-maps.md)   
 [AfxSocketInit](../Topic/AfxSocketInit.md)