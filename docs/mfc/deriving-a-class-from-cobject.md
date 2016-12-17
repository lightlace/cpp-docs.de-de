---
title: "Ableiten einer Klasse von CObject"
ms.custom: na
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "article"
f1_keywords: 
  - "CObject"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CObject-Klasse, Ableiten von"
  - "CObject-Klasse, Abgeleitete serialisierbare Klassen"
  - "DECLARE_DYNAMIC-Makro"
  - "DECLARE_DYNCREATE-Makro"
  - "DECLARE_SERIAL-Makro"
  - "Abgeleitete Klassen, aus CObject"
  - "Makros [C++], Serialisierung"
  - "Serialisierung [C++], Makros"
ms.assetid: 5ea4ea41-08b5-4bd8-b247-c5de8c152a27
caps.latest.revision: 11
caps.handback.revision: "7"
ms.author: "mblome"
manager: "ghogen"
---
# Ableiten einer Klasse von CObject
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Dieser Artikel beschreibt die minimale Schritte, die erforderlich sind, eine Klasse von [CObject](../mfc/reference/cobject-class.md) ableiten.  Andere `CObject`\-Klassenartikel beschreiben die Schritte, die erforderlich sind, um bestimmte `CObject`\-Funktionen, z Serialisierung und Diagnosendebugunterstützung zu nutzen.  
  
 Während der Erörterung `CObject`, schließen die Begriffe "Datei" an und "Implementierungsdatei" werden häufig verwendet.  Die Schnittstellendatei \(häufig aufgerufen die Headerdatei oder. H\-Datei\) enthält die Klassendeklaration sowie beliebige andere Informationen, die erforderlich sind, um die Klasse zu verwenden.  Die CPP\-Datei Implementierungsdatei \(oder die\) enthält die Klassendefinition sowie den Code, der die Klassenmemberfunktionen implementiert.  Beispielsweise für eine Klasse mit dem Namen `CPerson`, wird normalerweise eine Schnittstellendatei erstellen, die PERSON.H und benannt wurde, PERSON.CPP Implementierungsdatei benannte.  Für einige kleine Klassen, die nicht in Anwendungen verwendet werden, ist es auch einfacher, die Schnittstelle und Implementierung in eine einzelne CPP\-Datei zu kombinieren.  
  
 Sie können von vier Ebenen Funktionen auswählen, wenn eine Klasse von `CObject` abgeleitet wurde:  
  
-   Grundlegende Funktionalität: Keine Unterstützung für Ablaufklasseninformationens\- oder Serialisierung jedoch Einschließungsdiagnosenspeicherverwaltung.  
  
-   Grundlegende Funktionalität sowie Unterstützung für Ablaufklasseninformationen.  
  
-   Grundlegende Funktionalität sowie Unterstützung für Ablaufklasseninformationen und dynamische Erstellung.  
  
-   Grundlegende Funktionalität sowie Unterstützung für Ablaufklasseninformationen, dynamische Erstellung und Serialisierung.  
  
 Die Klassen, die zur Wiederverwendung vorgesehen sind \(die, die später als Basisklassen dient\), sollten Ablaufklassenunterstützung und Serialisierungsunterstützung mindestens beinhalten, wenn überhaupt zukünftige Serialisierungsanforderung werden vorweggenommen.  
  
 Sie wählen das Niveau der Funktionen, indem Sie bestimmte Deklarations\- und Implementierungsmakros in der Deklaration und die Implementierung von Klassen verwenden, die Sie von `CObject` ableiten.  
  
 In der folgenden Tabelle wird die Beziehung zwischen Makros an, die zur Stützserialisierung und auf die Laufzeitinformationen verwendet werden.  
  
### Makros verwendet Serialisierung und Laufzeit\-Information  
  
|Makro verwendet|CObject::IsKindOf|CRuntimeClass::<br /><br /> CreateObject|CArchive::operator \>\><br /><br /> CArchive::operator \<\<|  
|---------------------|-----------------------|--------------------------------------|---------------------------------------------------------|  
|Grundlegende Funktionalität `CObject`|nein|nein|nein|  
|`DECLARE_DYNAMIC`|ja|nein|nein|  
|`DECLARE_DYNCREATE`|ja|ja|nein|  
|`DECLARE_SERIAL`|ja|ja|ja|  
  
#### So grundlegende CObject\-Funktionalität verwenden  
  
1.  Verwenden Sie die normale C\+\+\-Syntax, um die Klasse von `CObject` abgeleitet \(oder einer Klasse abgeleitet von `CObject`\).  
  
     Im folgenden Beispiel wird den einfachsten Fall, die Ableitung einer Klasse von `CObject`:  
  
     [!CODE [NVC_MFCCObjectSample#1](../CodeSnippet/VS_Snippets_Cpp/NVC_MFCCObjectSample#1)]  
  
 Normalerweise jedoch sollten mehrere von `CObject`\-Memberfunktionen überschreiben, um die spezifischen Eigenschaften der neuen Klasse behandeln.  Beispielsweise können Sie normalerweise die `Dump`\-Funktion von `CObject` überschreiben, damit sowohl für den Inhalt der Klasse bereitzustellen.  Ausführliche Informationen, wie `Dump`, finden Sie im Artikel [Diagnose: Sichern des Objekt\-Inhalts](assetId:///727855b1-5a83-44bd-9fe3-f1d535584b59).  Sie können auch die `AssertValid`\-Funktion von `CObject` überschreiben, damit benutzerdefinierte Tests bereitstellen, um die Konsistenz der Datenmember der Klassenobjekte zu überprüfen.  Eine Beschreibung von, wie `AssertValid`, finden Sie unter [MFC ASSERT\_VALID und CObject::AssertValid](assetId:///7654fb75-9e9a-499a-8165-0a96faf2d5e6).  
  
 Der Artikel [Angeben von Ebenen der Funktionalität](../mfc/specifying-levels-of-functionality.md) beschreibt, wie anderen Ebenen der Funktionalität, einschließlich Ablaufklasseninformationen, Erstellung dynamischer Objekte und Serialisierung angibt.  
  
## Siehe auch  
 [Verwenden von CObject](../mfc/using-cobject.md)