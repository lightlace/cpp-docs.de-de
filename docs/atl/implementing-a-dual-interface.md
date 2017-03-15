---
title: "Implementing a Dual Interface | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "duale Schnittstellen, Implementieren"
  - "IDispatchImpl-Klasse, implementing dual interfaces"
ms.assetid: d1da3633-b445-4dcd-8a0a-3efdafada3ea
caps.latest.revision: 12
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 7
---
# Implementing a Dual Interface
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Sie können eine duale Schnittstelle mit der [IDispatchImpl](../atl/reference/idispatchimpl-class.md)\-Klasse implementieren, die eine Standardimplementierung der `IDispatch`\-Methoden in einer dualen Schnittstelle bereitstellt.  Weitere Informationen finden Sie unter [Implementing the IDispatch Interface](assetId:///0e171f7f-0022-4e9b-ac8e-98192828e945).  
  
 Um diese Klasse verwenden:  
  
-   Definieren Sie die duale Schnittstelle in einer Typbibliothek.  
  
-   Leiten Sie die Klasse von einer Spezialisierung von `IDispatchImpl` \(Übergabeninformationen über die Schnittstelle und die Typbibliothek als die Vorlagenargumente\).  
  
-   Fügen Sie einen Eintrag \(oder Einträge\) der COM\-Zuordnung hinzu, um die duale Schnittstelle durch `QueryInterface` verfügbar zu machen.  
  
-   Implementieren Sie den Teil der Schnittstelle in der Klasse.  
  
-   Stellen Sie sicher, dass die Typbibliothek, die die Schnittstellendefinition enthält, zu den Objekten zur Laufzeit verfügbar sind.  
  
## ATL\-Assistent für einfache Objekte  
 Wenn Sie eine neue Schnittstelle und eine neue Klasse erstellen möchten, um sie zu implementieren, können Sie [ATL fügt Klassendialogfeld hinzu](../ide/add-class-dialog-box.md) und dann [ATL\-Assistent für einfache Objekte](../atl/reference/atl-simple-object-wizard.md) verwenden.  
  
## Assistent zum Implementieren von Schnittstellen  
 Wenn Sie eine vorhandene Schnittstelle haben, können Sie [Assistent zum Implementieren von Schnittstellen](../atl/reference/adding-a-new-interface-in-an-atl-project.md) verwenden, um die erforderliche Basisklasse, die COM\-Zuordnungs\-Einträge und die Skelettmethodenimplementierungen einer vorhandenen Klasse hinzuzufügen.  
  
> [!NOTE]
>  Sie müssen möglicherweise die generierte Basisklasse anpassen, sodass die Hauptversionsnummer und die Nebenversionsnummer der Typbibliothek als Vorlagenargumente zu der `IDispatchImpl` Basisklasse übergeben werden.  Der Assistent zum Implementieren von Schnittstellen überprüft die Versionsnummer für Sie.  
  
## Implementieren von IDispatch  
 Sie können eine `IDispatchImpl` Basisklasse verwenden, um eine Implementierung einer Dispatchschnittstelle bereitzustellen, gerade vom Angeben des entsprechenden Eintrag in der COM\-Zuordnung \(mithilfe des [COM\_INTERFACE\_ENTRY2](../Topic/COM_INTERFACE_ENTRY2.md) oder [COM\_INTERFACE\_ENTRY\_IID](../Topic/COM_INTERFACE_ENTRY_IID.md)\-Makros\) solange Sie eine Typbibliothek verfügen, die eine entsprechende duale Schnittstelle beschrieben.  Es ist recht üblich, die `IDispatch`\-Schnittstelle implementieren auf diese Weise, zum Beispiel.  Der ATL\-Assistent für einfache Objekte und der Assistent zum Implementieren von Schnittstellen beide wird davon ausgegangen, dass Sie beabsichtigen, `IDispatch` auf diese Weise zu implementieren, sodass fügen sie den entsprechenden Eintrag der Zuordnung hinzu.  
  
> [!NOTE]
>  ATL bietet die [IDispEventImpl](../atl/reference/idispeventimpl-class.md) und [IDispEventSimpleImpl](../atl/reference/idispeventsimpleimpl-class.md)\-Klassen, die Ihnen helfen, Dispatchschnittstellen zu implementieren, ohne eine Typbibliothek benötigen, die die Definition einer kompatiblen duale Schnittstelle enthält.  
  
## Siehe auch  
 [Dual Interfaces and ATL](../atl/dual-interfaces-and-atl.md)