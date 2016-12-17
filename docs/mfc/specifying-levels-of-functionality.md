---
title: "Festlegen von Funktionalit&#228;tsebenen"
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
  - "CObject-Klasse, Hinzufügen von Funktionalität zu abgeleiteten Klassen"
  - "Unterstützung für dynamische Erstellung"
  - "Ebenen [C++]"
  - "Ebenen [C++], Funktionalität in CObject"
  - "Laufzeit [C++], Klasseninformation"
  - "run-time-Klasse, Informationsunterstützung"
  - "Serialisierung [C++], Cobject"
ms.assetid: 562669ba-c858-4f66-b5f1-b3beeea4f486
caps.latest.revision: 9
caps.handback.revision: "5"
ms.author: "mblome"
manager: "ghogen"
---
# Festlegen von Funktionalit&#228;tsebenen
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Dieser Artikel wird beschrieben, wie der folgenden Ebenen der Funktionalität dem [CObject](../mfc/reference/cobject-class.md) abgeleiteten Klasse hinzufügen:  
  
-   [Ablaufklasseninformationen](#_core_to_add_run.2d.time_class_information)  
  
-   [Dynamische Erstellungsunterstützung](#_core_to_add_dynamic_creation_support)  
  
-   [Die Serialisierungsunterstützung](#_core_to_add_serialization_support)  
  
 Eine allgemeine Beschreibung von `CObject`\-Funktionen, finden Sie im Artikel [Ableiten einer Klasse von CObject](../mfc/deriving-a-class-from-cobject.md).  
  
#### So Ablaufklasseninformationen hinzufügen  
  
1.  Ableiten der Klasse von `CObject`, wie im Artikel [Ableiten einer Klasse von CObject](../mfc/deriving-a-class-from-cobject.md) beschrieben.  
  
2.  Verwenden Sie das `DECLARE_DYNAMIC`\-Makro in der Klassendeklaration, wie hier gezeigt:  
  
     [!CODE [NVC_MFCCObjectSample#2](../CodeSnippet/VS_Snippets_Cpp/NVC_MFCCObjectSample#2)]  
  
3.  Verwenden Sie das `IMPLEMENT_DYNAMIC`\-Makro in der Implementierungsdatei \(.CPP\) der Klasse.  Dieses Makro verwendet als Argumente den Namen der Klasse und ihrer Basisklasse, wie folgt:  
  
     [!CODE [NVC_MFCCObjectSample#3](../CodeSnippet/VS_Snippets_Cpp/NVC_MFCCObjectSample#3)]  
  
> [!NOTE]
>  Legen Sie `IMPLEMENT_DYNAMIC` immer in die Implementierungsdatei \(.CPP\) für die Klasse ein.  Das Makro `IMPLEMENT_DYNAMIC` sollte nur einmal während einer Kompilierung ausgewertet werden und nicht in einer Schnittstellendatei deshalb verwendet werden \(.H\), die in mehr als einer Datei ggf. enthalten werden konnte.  
  
#### Um dynamische Erstellungsunterstützung hinzufügen  
  
1.  Ableiten der Klasse von `CObject`.  
  
2.  Verwenden Sie das `DECLARE_DYNCREATE`\-Makro in der Klassendeklaration.  
  
3.  Definieren Sie einen Konstruktor ohne Argumente \(ein Standardkonstruktor\).  
  
4.  Verwenden Sie das `IMPLEMENT_DYNCREATE`\-Makro in der Klassenimplementierungsdatei.  
  
#### So Serialisierungsunterstützung hinzufügen  
  
1.  Ableiten der Klasse von `CObject`.  
  
2.  Überschreiben Sie die `Serialize`\-Memberfunktion.  
  
    > [!NOTE]
    >  Wenn Sie `Serialize` direkt d. h aufrufen möchten Sie nicht das Objekt über einen Zeiger polymorphen serialisieren, weglassen Schritte 3 bis 5.  
  
3.  Verwenden Sie das `DECLARE_SERIAL`\-Makro in der Klassendeklaration.  
  
4.  Definieren Sie einen Konstruktor ohne Argumente \(ein Standardkonstruktor\).  
  
5.  Verwenden Sie das `IMPLEMENT_SERIAL`\-Makro in der Klassenimplementierungsdatei.  
  
> [!NOTE]
>  Ein "polymorpher Zeiger" zeigt auf ein Objekt eine Klasse \(A Aufruf es\) oder einem Objekt einer Klasse abgeleitet von A \(Sie sagen, B\).  Um von polymorphen einen Zeiger zu serialisieren, muss das Framework die Laufzeitklasse des Objekts bestimmen, das sie \(b\) serialisiert, da möglicherweise ein Objekt einer beliebigen Klasse ist, die von einer Basisklasse \(a\) berechnet wird.  
  
 Weitere Informationen darüber, wie die Serialisierung, wenn Sie die Klasse von `CObject` ableiten, finden Sie in Artikel [Dateien in MFC](../mfc/files-in-mfc.md) und [Serialisierung](../mfc/serialization-in-mfc.md).  
  
## Siehe auch  
 [Ableiten einer Klasse von CObject](../mfc/deriving-a-class-from-cobject.md)