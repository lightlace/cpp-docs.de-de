---
title: "CAtlArray Class"
ms.custom: na
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "reference"
f1_keywords: 
  - "ATL::CAtlArray"
  - "ATL.CAtlArray"
  - "CAtlArray"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CAtlArray class"
ms.assetid: 0b503aa8-2357-40af-a326-6654bf1da098
caps.latest.revision: 21
caps.handback.revision: "9"
ms.author: "mblome"
manager: "ghogen"
---
# CAtlArray Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Diese Klasse implementiert ein Arrayobjekt.  
  
## Syntax  
  
```  
  
      template<   
   typename E,  
   class ETraits = CElementTraits< E >   
>  
class CAtlArray  
```  
  
#### Parameter  
 *E*  
 Der Typ von den im Array gespeichert werden, Daten.  
  
 *ETraits*  
 Der Code verwendet, um Elemente zu kopieren oder verschieben.  
  
## Mitglieder  
  
### Methoden  
  
|||  
|-|-|  
|[add](../Topic/CAtlArray::Add.md)|Rufen Sie diese Methode auf, um ein Element am Arrayobjekt hinzuzufügen.|  
|[Append](../Topic/CAtlArray::Append.md)|Rufen Sie diese Methode auf, um den Inhalt von einem Array Ende von anderen hinzuzufügen.|  
|[AssertValid](../Topic/CAtlArray::AssertValid.md)|Rufen Sie diese Methode auf, um zu bestätigen, dass das Objekt gültig ist.|  
|[CAtlArray](../Topic/CAtlArray::CAtlArray.md)|Der \-Konstruktor.|  
|[~CAtlArray](../Topic/CAtlArray::~CAtlArray.md)|Der Destruktor.|  
|[Kopieren](../Topic/CAtlArray::Copy.md)|Rufen Sie diese Methode auf, um die Elemente aus einem Array zu anderen zu kopieren.|  
|[FreeExtra](../Topic/CAtlArray::FreeExtra.md)|Rufen Sie diese Methode auf, um eine leere Elemente aus dem Array zu entfernen.|  
|[GetAt](../Topic/CAtlArray::GetAt.md)|Rufen Sie diese Methode auf, um ein einzelnes Element aus dem Arrayobjekt abzurufen.|  
|[GetCount](../Topic/CAtlArray::GetCount.md)|Rufen Sie diese Methode auf, um die Anzahl von Elementen zurückzugeben, die im Array gespeichert sind.|  
|[GetData](../Topic/CAtlArray::GetData.md)|Rufen Sie diese Methode auf, um einen Zeiger auf das erste Element im Array zurückzugeben.|  
|[InsertArrayAt](../Topic/CAtlArray::InsertArrayAt.md)|Rufen Sie diese Methode auf, um ein Array in andere einzufügen.|  
|[InsertAt](../Topic/CAtlArray::InsertAt.md)|Rufen Sie diese Methode auf, um ein neues Element \(oder mehrere Kopien eines Elements\) in das Arrayobjekt einzufügen.|  
|[IsEmpty](../Topic/CAtlArray::IsEmpty.md)|Rufen Sie diese Methode auf, um zu testen, wenn das Array leer ist.|  
|[RemoveAll](../Topic/CAtlArray::RemoveAll.md)|Rufen Sie diese Methode auf, um alle Elemente aus Arrayobjekt zu entfernen.|  
|[RemoveAt](../Topic/CAtlArray::RemoveAt.md)|Rufen Sie diese Methode auf, um eine oder mehrere Elemente aus dem Array zu entfernen.|  
|[SetAt](../Topic/CAtlArray::SetAt.md)|Rufen Sie diese Methode auf, um den Wert eines Elements im Arrayobjekt festzulegen.|  
|[SetAtGrow](../Topic/CAtlArray::SetAtGrow.md)|Rufen Sie diese Methode auf, um den Wert eines Elements im Arrayobjekt festgelegt und das Array nach Bedarf erweitern.|  
|[SetCount](../Topic/CAtlArray::SetCount.md)|Rufen Sie diese Methode auf, um die Größe des Arrayobjekts festzulegen.|  
  
### Operatoren  
  
|||  
|-|-|  
|[Operator &#91;&#93;](../Topic/CAtlArray::operator.md)|Rufen Sie diesen Operator auf, um einen Verweis auf ein Element im Array zurückzugeben.|  
  
### Typedefs  
  
|||  
|-|-|  
|[INARGTYPE](../Topic/CAtlArray::INARGTYPE.md)|Der für das Hinzufügen von Elementen in das Array zu verwenden, Datentyp.|  
|[OUTARGTYPE](../Topic/CAtlArray::OUTARGTYPE.md)|Der für das Abrufen von Elementen aus dem Array zu verwenden, Datentyp.|  
  
## Hinweise  
 **CAtlArray** stellt Methoden zum Erstellen und Verwalten eines Arrays Elemente eines benutzerdefinierten Typs bereit.  Obwohl ähnlich Standard\-C\-Arrays, kann das **CAtlArray**\-Objekt dynamisch verkleinern und bei Bedarf wachsen.  Die Start des Arrayindexes immer an Position 0 und der Obergrenze behoben werden können oder ermöglicht werden, um zu erweitern, da neue Elemente hinzugefügt werden.  
  
 Für Arrays mit einer geringen Anzahl von Elementen, kann die ATL\-Klasse [CSimpleArray](../../atl/reference/csimplearray-class.md) verwendet werden.  
  
 **CAtlArray** ist zu **CArray**\-Klasse MFC eng miteinander in Beziehung und in einem MFC\-Projekt, obwohl ohne Serialisierungsunterstützung arbeiten.  
  
 Weitere Informationen finden Sie unter [ATL\-Auflistungsklassen](../../atl/atl-collection-classes.md).  
  
## Anforderungen  
 **Header:** atlcoll.h  
  
## Siehe auch  
 [MMXSwarm\-Beispiel](../../top/visual-cpp-samples.md)   
 [DynamicConsumer\-Beispiel](../../top/visual-cpp-samples.md)   
 [UpdatePV\-Beispiel](../../top/visual-cpp-samples.md)   
 [Marquee\-Beispiel](../../top/visual-cpp-samples.md)   
 [CArray Class](../../mfc/reference/carray-class.md)   
 [Class Overview](../../atl/atl-class-overview.md)