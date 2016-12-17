---
title: "Zugreifen auf Laufzeit-Klasseninformationen"
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
  - "Klassen [C++], Laufzeit-Klasseninformationen"
  - "CObject-Klasse, Zugreifen auf Laufzeit-Klasseninformationen"
  - "CObject-Klasse, und RTTI"
  - "CObject-Klasse, Verwenden der IsKindOf-Methode"
  - "CObject-Klasse, Verwenden vom RUNTIME_CLASS-Makro"
  - "IsKindOf method-Methode"
  - "RTTI-Compileroption"
  - "Laufzeit"
  - "Laufzeit, Klasseninformation"
  - "run-time-Klasse"
  - "run-time-Klasse, Zugriff auf Informationen"
  - "RUNTIME_CLASS-Makro"
  - "RUNTIME_CLASS-Makro, Verwenden"
ms.assetid: 3445a9af-0bd6-4496-95c3-aa59b964570b
caps.latest.revision: 11
caps.handback.revision: "7"
ms.author: "mblome"
manager: "ghogen"
---
# Zugreifen auf Laufzeit-Klasseninformationen
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Dieser Artikel beschreibt z auf Informationen über die Klasse eines Objekts zur Laufzeit.  
  
> [!NOTE]
>  MFC verwendet keine Unterstützung [Laufzeit\-Typeninformationen](../cpp/run-time-type-information.md) \(RTTI\), die in Visual C\+\+ 4.0 eingeführt wurde.  
  
 Wenn Sie die Klasse von [CObject](../mfc/reference/cobject-class.md) abgeleitet und das **DEKLARIEREN**\_**DYNAMISCH** und `IMPLEMENT_DYNAMIC`, `DECLARE_DYNCREATE` und `IMPLEMENT_DYNCREATE` oder die `DECLARE_SERIAL` und `IMPLEMENT_SERIAL`, die Makros im Artikel [Ableiten einer Klasse von CObject](../mfc/deriving-a-class-from-cobject.md) erläutert werden verwendet haben, hat die `CObject`\-Klasse die Möglichkeit, die genauen Klasse eines Objekts zur Laufzeit zu bestimmen.  
  
 Diese Fähigkeit ist besonders hilfreich, wenn zusätzliche Typüberprüfung von Funktionsargumenten erforderlich ist und wenn Sie für besondere Zwecke auf Grundlage der Klasse eines Objekts müssen Code schreiben.  Davon wird jedoch normalerweise nicht empfohlen, da dies die Funktionalität von virtuellen Funktionen dupliziert.  
  
 Die `CObject`\-Memberfunktion `IsKindOf` kann verwendet werden, um zu bestimmen, ob ein bestimmtes Objekt einer angegebenen Klasse gehört, oder wenn von einer bestimmten Klasse abgeleitet ist.  Das Argument für `IsKindOf` ist ein `CRuntimeClass`\-Objekt, das Sie mithilfe des `RUNTIME_CLASS`\-Makros mit dem Namen der Klasse abrufen können.  
  
### Um das RUNTIME\_CLASS\-Makro verwenden  
  
1.  Verwenden Sie `RUNTIME_CLASS` mit dem Namen der Klasse, wie hier gezeigt für die Klasse `CObject`:  
  
     [!CODE [NVC_MFCCObjectSample#4](../CodeSnippet/VS_Snippets_Cpp/NVC_MFCCObjectSample#4)]  
  
 Sie müssen selten auf das Ablaufklassenobjekt direkt zugreifen.  Eine weitere allgemeine Verwendung besteht, das `IsKindOf` Ablaufklassenobjekt zur Funktion, wie im folgenden Verfahren dargestellt zu übergeben.  Die `IsKindOf`\-Funktionstests ein Objekt, festzustellen, ob es einer bestimmten Klasse gehört.  
  
#### Um die IsKindOf\-Funktion verwenden  
  
1.  Stellen Sie sicher, dass die Klasse Ablaufklassenunterstützung hat.  Das heißt, muss die Klasse direkt oder indirekt von `CObject` abgeleitet werden und verwendet das **DEKLARIEREN**\_**DYNAMISCH** und `IMPLEMENT_DYNAMIC`, `DECLARE_DYNCREATE` und `IMPLEMENT_DYNCREATE` oder die `DECLARE_SERIAL` und `IMPLEMENT_SERIAL`, die Makros im Artikel [Ableiten einer Klasse von CObject](../mfc/deriving-a-class-from-cobject.md) erläutert werden.  
  
2.  Rufen Sie die Memberfunktion `IsKindOf` für Objekte dieser Klasse, mithilfe des Makros `RUNTIME_CLASS` auf, um das Argument `CRuntimeClass` zu generieren, wie hier gezeigt:  
  
     [!CODE [NVC_MFCCObjectSample#2](../CodeSnippet/VS_Snippets_Cpp/NVC_MFCCObjectSample#2)]  
  
     [!CODE [NVC_MFCCObjectSample#5](../CodeSnippet/VS_Snippets_Cpp/NVC_MFCCObjectSample#5)]  
  
    > [!NOTE]
    >  IsKindOf gibt **TRUE** zurück, wenn das Objekt ein Member der angegebenen Klasse oder einer Klasse ist, die von der angegebenen Klasse abgeleitet wird.  `IsKindOf` unterstützt Mehrfachvererbung nicht virtuelle oder Basisklassen, obwohl Sie Mehrfachvererbung für die abgeleiteten Foundations\-Klassen ggf. Microsoft verwenden können.  
  
 Ein Verwendung von Ablaufklasseninformationen ist in der dynamischen Erstellung von Objekten.  Dieser Prozess wird im Artikel [Dynamisches Erstellen von Objekten](../mfc/dynamic-object-creation.md) erläutert.  
  
 Ausführlichere Informationen zur Serialisierung und Laufzeitklasseninformationen finden Sie in Artikel [Dateien in MFC](../mfc/files-in-mfc.md) und [Serialisierung](../mfc/serialization-in-mfc.md).  
  
## Siehe auch  
 [Verwenden von CObject](../mfc/using-cobject.md)