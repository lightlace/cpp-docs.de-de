---
title: Verwenden von CObject | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: CObject
dev_langs: C++
helpviewer_keywords:
- examples [MFC], CObject
- root base class for MFC
- derived classes [MFC], from CObject
- MFC, base class
- CObject class [MFC]
ms.assetid: d0cd19bb-2856-4b41-abbc-620fd64cb223
caps.latest.revision: "9"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 17bffb412975cfc6a97eae8b30aff2514a2e1d93
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="using-cobject"></a>Verwenden von CObject
[CObject](../mfc/reference/cobject-class.md) ist die Stamm-Basisklasse für die meisten der Microsoft Foundation Class-Bibliothek (MFC). Die `CObject` Klasse enthält viele nützliche Features, die Sie in eine eigene Anwendung-Objekte, einschließlich Serialisierungsunterstützung, Laufzeit Klasseninformationen und Diagnoseausgaben integrieren möchten. Wenn Sie eine Klasse von ableiten `CObject`, Ihre Klasse kann dies ausnutzen `CObject` Funktionen.  
  
## <a name="what-do-you-want-to-do"></a>Was möchten Sie tun  
  
-   [Leiten Sie eine Klasse von CObject](../mfc/deriving-a-class-from-cobject.md)  
  
-   [Unterstützung für Laufzeit Klasseninformationen, dynamische Erstellung und Serialisierung Meine abgeleiteten Klasse hinzufügen](../mfc/specifying-levels-of-functionality.md)  
  
-   [Zugriff zur Laufzeit-Klasseninformationen](../mfc/accessing-run-time-class-information.md)  
  
-   [Dynamisches Erstellen von Objekten](../mfc/dynamic-object-creation.md)  
  
-   [Sichern von Daten für das Objekt zu Diagnosezwecken](http://msdn.microsoft.com/en-us/727855b1-5a83-44bd-9fe3-f1d535584b59)  
  
-   Überprüfen der interne Zustand des Objekts (finden Sie unter [MFC ASSERT_VALID und CObject:: AssertValid](http://msdn.microsoft.com/en-us/7654fb75-9e9a-499a-8165-0a96faf2d5e6))  
  
-   [Haben Sie die Klasse selbst in den permanenten Speicher serialisieren.](../mfc/serialization-in-mfc.md)  
  
-   Eine Liste der [häufig gestellte Fragen zu CObject](../mfc/cobject-class-frequently-asked-questions.md)  
  
## <a name="see-also"></a>Siehe auch  
 [Konzepte](../mfc/mfc-concepts.md)   
 [Allgemeine MFC-Themen](../mfc/general-mfc-topics.md)   
 [CRuntimeClass-Struktur](../mfc/reference/cruntimeclass-structure.md)   
 [Dateien](../mfc/files-in-mfc.md)   
 [Serialisierung](../mfc/serialization-in-mfc.md)

