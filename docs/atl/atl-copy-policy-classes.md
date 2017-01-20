---
title: "ATL Copy Policy Classes"
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
  - "_Copy class"
  - "_CopyInterface class"
  - "Klassen [C++], copy policy"
  - "copy policy classes [C++]"
  - "Daten [C++], ATL"
ms.assetid: 06704b68-d318-4c5d-a65b-71457fe9d00d
caps.latest.revision: 13
caps.handback.revision: "7"
ms.author: "mblome"
manager: "ghogen"
---
# ATL Copy Policy Classes
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Kopierrichtlinienklassen sind [Hilfsklassen](../atl/utility-classes.md), das verwendet wird, um Daten zu initialisieren, zu kopieren und zu löschen.  Kopierrichtlinienklassen ermöglichen es Ihnen, Kopiensemantik für jeden Typ Daten definieren, und Konvertierungen zwischen unterschiedlichen Datentypen Daten.  
  
 ATL verwendet Kopierrichtlinienklassen in den Implementierungen der folgenden Vorlagen:  
  
-   [CComEnumImpl](../atl/reference/ccomenumimpl-class.md)  
  
-   [IEnumOnSTLImpl](../atl/reference/ienumonstlimpl-class.md)  
  
-   [ICollectionOnSTLImpl](../atl/reference/icollectiononstlimpl-class.md)  
  
 Indem sie Informationen kapselten, die erforderlich sind, um Daten in einer Kopierrichtlinienklasse zu kopieren oder zu konvertieren, die als Vorlagenargument übergeben werden kann, muss die ATL\-Entwickler für extreme Wiederverwendbarkeit dieser Klassen bereitgestellt.  Wenn Sie beispielsweise eine Auflistung mithilfe eines beliebigen Datentyps implementieren müssen, ist alle, die Sie angeben müssen, die entsprechende Kopierrichtlinienklassen; Sie müssen den Code nie berühren, der die Auflistung implementiert.  
  
## Definition  
 Definitionsgemäß ist eine Klasse, die die folgenden statischen Funktionen bereitstellt, eine Kopierrichtlinienklasse:  
  
 `static void init(` `DestinationType` `* p);`  
  
 `static HRESULT copy(` `DestinationType` `* pTo, const`  `SourceType` `* pFrom);`  
  
 `static void destroy(` `DestinationType` `* p);`  
  
 Sie können die Typen `DestinationType` und *SourceType* durch beliebige Datentypen für jede Kopierrichtlinienklassen ersetzen.  
  
> [!NOTE]
>  Obwohl Sie Kopierrichtlinienklassen für alle beliebigen Datentypen definieren können, sollte Verwendung von Klassen in ATL\-Code die Typen einschränken, die sinnvoll sind.  Wenn beispielsweise eine Kopierrichtlinienklasse mit Auflistungs\- oder Enumeratorimplementierungen ATL, `DestinationType` muss ein Typ sein verwendet, der als Parameter in einer COM\-Schnittstellen\-Methode verwendet werden kann.  
  
 Verwenden Sie **init**, um Daten, **copy**, um Daten zu kopieren und **destroy** zu initialisieren, um die Daten auszutauschen.  Die genaue Bedeutung der Initialisierung, Kopieren und Zerstörung sind die Domäne der Kopierrichtlinienklasse und werden abhängig von den verwendeten Datentypen variieren.  
  
 Es gibt zwei Anforderungen bei der Verwendung und Implementierung von einer Kopierrichtlinienklasse:  
  
-   Der erste Parameter zu **copy** muss einen Zeiger auf die Daten nur erhalten, die Sie zuvor mit dem **init** initialisiert haben.  
  
-   **destroy** muss einen Zeiger auf die Daten nur ganz ausschließen, die Sie zuvor mit dem **init** oder über **copy** kopiert initialisiert haben.  
  
## Standardimplementierungen  
 ATL stellt zwei Kopierrichtlinienklassen in Form von den **\_Copy** und **\_CopyInterface** Vorlagenklassen bereit:  
  
-   Die Klasse ermöglicht **\_Copy** homogenes nur kopieren \(keine Konvertierung zwischen Datentypen\) wie sie nur einen einzelnen Vorlagenparameter bietet, um `DestinationType` und *SourceType* anzugeben.  Die generische Implementierung dieser Vorlage enthält keine Initialisierung oder Zerstörungscode und `memcpy` verwendet, um die Daten zu kopieren.  ATL stellt auch Spezialisierungen von **\_Copy** für **VARIANT**, `LPOLESTR`, **OLEVERB** und **CONNECTDATA** Datentypen.  
  
-   Die **\_CopyInterface**\-Klasse stellt eine Implementierung für das Kopieren von Schnittstellenzeigern nach Standard\-COM\-Regeln bereit.  Auch einmal können diese Klasse homogenes nur kopieren, sodass sie verwendet einfache Zuweisung und einen Aufruf `AddRef`, um die Kopie auszuführen.  
  
## Benutzerdefinierte Implementierungen  
 In der Regel müssen Sie eigene Kopierrichtlinienklassen für das Kopieren heterogene definieren \(das heißt, Konvertierung zwischen Datentypen\).  Für einige Beispiele von benutzerdefinierten Kopierrichtlinienklassen, berücksichtigen Sie die Dateien VCUE\_Copy.h und VCUE\_CopyString.h im [ATLCollections](../top/visual-cpp-samples.md) Beispiel.  Diese Dateien enthalten zwei Vorlagenkopierrichtlinienklassen, `GenericCopy` und `MapCopy`, sowie einige Spezialisierungen von `GenericCopy` für unterschiedliche Datentypen.  
  
### GenericCopy  
 `GenericCopy` ermöglicht, das *SourceType* und `DestinationType` als Vorlagenargumente anzugeben.  Hier ist das häufigste Form der `GenericCopy`\-Klasse von VCUE\_Copy.h:  
  
 [!CODE [NVC_ATL_COM#30](../CodeSnippet/VS_Snippets_Cpp/NVC_ATL_COM#30)]  
  
 VCUE\_Copy.h enthält außerdem die folgenden Spezialisierungen dieser Klasse: `GenericCopy<BSTR>`, `GenericCopy<VARIANT, BSTR>`, `GenericCopy<BSTR, VARIANT>`.  VCUE\_CopyString.h enthält Spezialisierungen für das Kopieren von **std::string**s: `GenericCopy<std::string>`, `GenericCopy<VARIANT, std::string>` und `GenericCopy<BSTR, std::string>`.  Sie können `GenericCopy` erhöhen, indem Sie weitere Spezialisierungen von eigenen bereitgestellt haben.  
  
### MapCopy  
 `MapCopy` wird davon ausgegangen, dass die Daten, die kopiert werden, in einer STL\-Format Zuordnung gespeichert werden, und ermöglicht es Ihnen, den Typ der Zuordnung anzugeben, in dem die Daten und der Zieltyp gespeichert werden.  Die Implementierung der Klasse verwendet nur die Typdefinitionen, die von der *MapType\-Klasse*, um den Typ der Quelldaten zu bestimmen angegeben werden und die entsprechende `GenericCopy`\-Klasse aufzurufen.  Keine Spezialisierungen dieser Klasse erforderlich.  
  
 [!CODE [NVC_ATL_COM#31](../CodeSnippet/VS_Snippets_Cpp/NVC_ATL_COM#31)]  
  
## Siehe auch  
 [Implementing an STL\-Based Collection](../atl/implementing-an-stl-based-collection.md)   
 [ATLCollections\-Beispiel](../top/visual-cpp-samples.md)