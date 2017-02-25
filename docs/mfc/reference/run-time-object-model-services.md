---
title: "Objektmodelldienste zur Laufzeit | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vc.mfc.macros"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Objektmodelldienste-Makros zur Laufzeit"
ms.assetid: 4a3e79df-2ee3-43a4-8193-20298828de85
caps.latest.revision: 15
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 16
---
# Objektmodelldienste zur Laufzeit
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Die Klassen [CObject](../../mfc/reference/cobject-class.md) und [CRuntimeClass](../../mfc/reference/cruntimeclass-structure.md) kapseln einige Objektdienste, einschließlich Zugriff auf den Ablaufklasseninformationen, zur Serialisierung und der Erstellung dynamischer Objekte.  Alle Klassen, die von `CObject` abgeleitet werden, erben diese Funktionalität.  
  
 Zugriff auf den Ablaufklasseninformationen, können Sie Informationen zu einem Objekts zur Laufzeit zu bestimmen.  Die Fähigkeit, die Klasse eines Objekts zu bestimmen zur Laufzeit ist hilfreich, wenn Sie zusätzliche Typüberprüfung von Funktionsargumenten benötigen und wenn Sie für besondere Zwecke auf Grundlage der Klasse eines Objekts müssen Code schreiben.  Ablaufklasseninformationen werden nicht direkt über die Programmiersprache C\+\+ unterstützt.  
  
 Serialisierung ist der Prozess des Schreibens oder der Lesen der Inhalte von Objekten in oder aus einer Datei.  Sie können die Serialisierung verwenden, um den Inhalt des Objekts zu speichern, wenn die Anwendung beendet.  Das Objekt kann von der Datei dann gelesen werden, falls die Anwendung neu gestartet wird.  Solche Datenobjekte sollen "erhalten."  
  
 Erstellung dynamischer Objekte Ermöglicht es, ein Objekt einer angegebenen Klasse zur Laufzeit zu erstellen.  Beispielsweise müssen Dokument, Ansicht und Frameobjekte dynamische Erstellung unterstützen, da das Framework diese dynamisch erstellen.  
  
 Die folgende Tabelle zeigt die MFC\-Makros auf, die Ablaufklasseninformationen, Serialisierung und dynamische Erstellung unterstützen.  
  
 Weitere Informationen über diese Ablaufobjektdienstleistungen und zum, finden Sie im Artikel [CObject\-Klasse: Zugreifen auf Ablaufklasseninformationen](../../mfc/accessing-run-time-class-information.md).  
  
### Laufzeitobjektmodell enthält Makros aus  
  
|||  
|-|-|  
|[DECLARE\_DYNAMIC](../Topic/DECLARE_DYNAMIC.md)|Ermöglicht den Zugriff auf die Ablaufklasseninformationen \(muss in der Klassendeklaration verwendet werden\).|  
|[DECLARE\_DYNCREATE](../Topic/DECLARE_DYNCREATE.md)|Verwendung dynamischer Erstellung und Zugriff auf den Ablaufklasseninformationen \(muss in der Klassendeklaration verwendet werden\).|  
|[DECLARE\_SERIAL](../Topic/DECLARE_SERIAL.md)|Ermöglicht Serialisierung und Zugriff auf den Ablaufklasseninformationen \(muss in der Klassendeklaration verwendet werden\).|  
|[IMPLEMENT\_DYNAMIC](../Topic/IMPLEMENT_DYNAMIC.md)|Ermöglicht den Zugriff auf die Ablaufklasseninformationen \(muss in die Klassenimplementierung verwendet werden\).|  
|[IMPLEMENT\_DYNCREATE](../Topic/IMPLEMENT_DYNCREATE.md)|Verwendung dynamischer Erstellung und auf die Laufzeitinformationen \(muss in die Klassenimplementierung verwendet werden\).|  
|[IMPLEMENT\_SERIAL](../Topic/IMPLEMENT_SERIAL.md)|Serialisierung nicht und Zugriff auf den Ablaufklasseninformationen \(muss in die Klassenimplementierung verwendet werden\).|  
|[RUNTIME\_CLASS](../Topic/RUNTIME_CLASS.md)|Gibt der `CRuntimeClass`\-Struktur zurück, die mit benannten Klasse entspricht.|  
  
 OLE erfordert häufig die dynamische Erstellung von Objekten zur Laufzeit.  Zum Beispiel muss eine OLE\-Serveranwendung in der Lage sein, OLE\-Elemente als Antwort auf eine Anforderung von einem Client dynamisch zu erstellen.  Außerdem muss ein Automatisierungsserver in der Lage sein, Elemente auf Anforderungen von den Automatisierungsclients zu erstellen.  
  
 Die Microsoft Foundation Class\-Bibliothek stellt zwei Makros bereit, die mit OLE spezifisch sind.  
  
### Die dynamische Erstellung von OLE\-Objekten  
  
|||  
|-|-|  
|[DECLARE\_OLECREATE](../Topic/DECLARE_OLECREATE.md)|Ermöglicht die OLE\-Automatisierung von zu erstellenden Objekte.|  
|[IMPLEMENT\_OLECREATE](../Topic/IMPLEMENT_OLECREATE.md)|Ermöglicht die vom OLE\-System erstellt werden Objekte.|  
  
## Siehe auch  
 [MFC\-Makros, globale Funktionen und globale Variablen](../../mfc/reference/mfc-macros-and-globals.md)