---
title: "Einschr&#228;nkungen der Datenbindung"
ms.custom: na
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Datenbindung [C++], Einschränkungen in Visual C++"
ms.assetid: 376d7738-5252-4caa-adda-a5486ab2a2a2
caps.latest.revision: 8
caps.handback.revision: "8"
ms.author: "mblome"
manager: "ghogen"
---
# Einschr&#228;nkungen der Datenbindung
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Die Datenbindung bietet optimale Voraussetzungen, um schnell und einfach Datenanwendungen zu entwickeln.  Die aktuellen Datenbindungs\-Steuerelemente basieren jedoch auf dem Zwei\-Ebenen\-Modell.  
  
## Skalierbarkeit  
 Datengebundene ADO\-Steuerelemente können ausschließlich auf Daten aus dem ADO\-Datensteuerelement zugreifen.  Datengebundene RDO\-Steuerelemente können ausschließlich auf Daten aus dem RDO\-Remote\-Datensteuerelement zugreifen.  Für das RDO\-Remote\-Datensteuerelement kann keine andere Architektur als das Zwei\-Ebenen\-Modell verwendet werden, was dazu führt, dass der Datenbankserver sämtliche Datenanforderungen direkt empfängt.  Um die direkte Verbindung mit dem Datenbankserver zu vermeiden, schreiben Sie einen Anbieter, der den Zugriff auf Geschäfts\- und Datenobjekte der mittleren Ebene ermöglicht.  Auf diese Weise stellt das ADO\-Datensteuerelement eine Verbindung mit diesen Objekten und nicht mit dem Datenbankserver her.  Solche Objekte der mittleren Ebene können in einem Transaktionsserver, z. B. COM\+ 1.0\-Diensten, zwischengespeichert und verwaltet werden.  
  
## Versionskontrolle und Verteilung  
 Sobald neue Steuerelementversionen herausgegeben werden, muss die Anwendung mit den neuen Versionen getestet werden.  Wenn eine weitere Anwendung auf dem Computer eines Benutzers installiert wird, die über andere Steuerelementversionen verfügt, muss diese Anwendung überprüft werden.  Schließlich müssen neu herausgegebene Steuerelementversionen an die Benutzer der jeweiligen Anwendungen verteilt werden.  
  
 **Treiber und Anbieter**  
  
 Die Datenbindung kann nur so viel leisten wie der verwendete ODBC\-Treiber oder OLE DB\-Anbieter.  Da Treiber und Anbieter für die Offenlegung von Daten gegenüber Datensteuerelementen zuständig sind, sollte unbedingt sichergestellt werden, dass die verwendeten Treiber und Anbieter die erforderlichen Funktionen unterstützen.  Wenn Sie sich für einen Anbieter oder Treiber entschieden haben, müssen Sie auch gewährleisten, dass die Benutzer den Treiber oder Anbieter installiert haben.  Dazu gehört auch die Installation etwaiger Middleware, die vom Treiber oder Anbieter benötigt wird.  Beispielsweise sollten Benutzer, die ODBC Oracle\-Konnektivität benötigen, nicht nur einen Oracle ODBC\-Treiber installieren, sondern auch die SQL\*Net\-Middleware von Oracle.  Um Konnektivität mit Oracle 7.3\-Servern zu gewährleisten, wird der Oracle ODBC\-Treiber von Microsoft empfohlen.  
  
 **Programmierbarkeit**  
  
 Da ActiveX\-Steuerelemente als Blackboxkomponenten entwickelt wurden, hängt die Programmierbarkeit davon ab, welchen Zugriff der Entwickler auf die Schnittstellen des Steuerelements hat.  Im Datenbindungsmodell des Ressourcen\-Editors wird dies mittels [Wrapperklassen](../../data/ado-rdo/wrapper-classes.md) implementiert, die vom Assistenten zum Einfügen von ActiveX\-Steuerelementen generiert werden.  Wenn der Assistent keine Co\-Klasse erkennen kann, wird auch keine Wrapperklasse generiert, sodass kein programmgesteuerter Zugriff erfolgt.  
  
 Trotz dieser Einschränkungen ermöglicht die Datenbindung die schnelle Erstellung von Prototypdatenanwendungen mithilfe von Visual C\+\+.  In Fällen, in denen die schnelle Entwicklung eine Rolle spielt, sollte für das Anwendungsdesign die Datenbindung in Betracht gezogen werden.  
  
## Siehe auch  
 [Datenbindung mit ActiveX\-Steuerelementen in Visual C\+\+](../../data/ado-rdo/databinding-with-activex-controls-in-visual-cpp.md)