---
title: "CFixedStringT: Example of a Custom String Manager"
ms.custom: na
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "reference"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CFixedStringT class, using a custom string manager"
ms.assetid: 1cf11fd7-51b8-4b94-87af-02bc25f47dd6
caps.latest.revision: 11
caps.handback.revision: "7"
ms.author: "mblome"
manager: "ghogen"
---
# CFixedStringT: Example of a Custom String Manager
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Die ATL\-Bibliothek implementiert ein Beispiel eines benutzerdefinierten Zeichenfolgenmanagers, der von Klasse [CFixedStringT](../atl-mfc-shared/reference/cfixedstringt-class.md) verwendet wird, **CFixedStringMgr** aufgerufen.  `CFixedStringT` wird von [CStringT](../atl-mfc-shared/reference/cstringt-class.md) abgeleitet und eine Zeichenfolge implementiert, die die Textdaten als Teil des `CFixedStringT`\-Objekts selbst, solange die Zeichenfolge kleiner ist als die Länge zuordnet, die vom **t\_nChars** Vorlagenparameter aus `CFixedStringT` angegeben wird.  Mit dieser Vorgehensweise muss die Zeichenfolge nicht den Heap vorhanden, es sei denn, die Länge der Zeichenfolge über der festen Größe des Puffers hinaus vergrößert.  Da `CFixedStringT` nicht immer einen Heap verwendet, um die Zeichenfolgendaten zuzuordnen, kann er **CAtlStringMgr** nicht als Zeichenfolgenmanager verwenden.  Es verwendet einen benutzerdefinierten Zeichenfolgenmanager \(**CFixedStringMgr**\) und implementiert die Schnittstelle [IAtlStringMgr](../atl-mfc-shared/reference/iatlstringmgr-class.md).  Diese Schnittstelle wird in [Implementierung eines benutzerdefinierten Zeichenfolgen\-Managers erweiterte \(Methode\)](../atl-mfc-shared/implementation-of-a-custom-string-manager-advanced-method.md) erläutert.  
  
 Der Konstruktor für **CFixedStringMgr** akzeptiert drei Parameter:  
  
-   Ein Zeiger **pData:** zur festen verwendet werden `CStringData`\-Struktur.  
  
-   **nChars:** die maximale Anzahl von Zeichen, die die `CStringData`\-Struktur enthalten kann.  
  
-   Ein Zeiger **pMgr:**  zur `IAtlStringMgr`\-Schnittstelle eines "Backup\-Zeichenfolgenmanagers."  
  
 Der Konstruktor speichert die Werte von `pData` und von **pMgr** in den jeweiligen Membervariablen \(`m_pData` und **m\_pMgr**\).  Es stellt dann die Länge des Puffers auf Null, die verfügbare Länge gleich die maximale Größe des feste Puffergröße und den Verweiszähler bis \- 1.  Der Verweiszählerwert gibt den Puffer wird gesperrt und diese Instanz von **CFixedStringMgr** als der Zeichenfolgenmanager verwenden an.  
  
 Das Markieren des Puffers als verschlossenes verhindert andere `CStringT`\-Instanzen am Anhalten eines freigegebenen Verweises auf Puffer.  Wenn `CStringT` anderen Instanzen zulässig wäre, um den Puffer freizugeben, ist es für den Puffer möglich sein, der von zu löschenden enthalten war, `CFixedStringT`, während andere Zeichenfolgen weiterhin den verwendeten Puffer.  
  
 **CFixedStringMgr** ist eine vollständige Implementierung der `IAtlStringMgr`\-Schnittstelle.  Die Implementierung der Methode wird jedoch erläutert.  
  
## Implementierung von CFixedStringMgr::Allocate  
 Die Implementierung von **CFixedStringMgr::Allocate** überprüft zuerst, anzuzeigen, wenn die angeforderte Größe der Zeichenfolge kleiner oder gleich der Größe des feste Puffergröße ist \(im gespeichert `m_pData`\-Member\).  Wenn der feste Puffer groß genug ist, sperrt **CFixedStringMgr** den Puffer mit einer festen Länge Null.  Solange die Zeichenfolgenlänge nicht über die Größe des festen Puffers hinaus vergrößert, muss `CStringT` nicht den Puffer neu reservieren.  
  
 Wenn die angeforderte Größe der Zeichenfolge größer, leitet der feste Puffer **CFixedStringMgr** die Anforderung an das Backup String Manager weiter.  Der Backup\-Zeichenfolgenmanager wird angenommen, dass den Puffer vom Heap zuzuordnen.  jedoch vor dem Zurückgeben dieses Puffers **CFixedStringMgr**, sperrt den Puffer und ersetzt den Zeichenfolgen\-Managerzeiger des Puffers durch einen Zeiger auf **CFixedStringMgr**\-Objekt.  Dadurch wird sichergestellt, dass versucht, den Puffer durch `CStringT` neu belegen oder freizugeben in **CFixedStringMgr** aufrufen.  
  
## Implementierung von CFixedStringMgr::ReAllocate  
 Die Implementierung von **CFixedStringMgr::ReAllocate** ist mit der Implementierung von **Allocate** sehr ähnlich.  
  
 Wenn der Puffer, der neu zugeordnet wird, der feste Puffer ist und die angeforderte Puffergröße kleiner als der feste Puffer ist, ist keine Zuordnung ausgeführt.  Wenn der Puffer, der neu zugeordnet ist, nicht der feste Puffer ist, es muss ein Puffer sein, der mit dem Backup\-Manager zugeordnet ist.  In diesem Fall wird der Backup\-Manager verwendet, um den Puffer neu belegen.  
  
 Wenn der Puffer, der neu zugeordnet wird, der feste Puffer ist und die neue Puffergröße zu groß ist, innerhalb des feste Puffergröße anpassen, ordnet **CFixedStringMgr** einen neuen Puffer mithilfe des Backup\-Managers zu.  Der Inhalt des feste Puffergröße wird dann in den neuen Puffer kopiert.  
  
## Implementierung von CFixedStringMgr::Free  
 Die Implementierung von **CFixedStringMgr::Free** folgt dem gleichen Muster wie **Allocate** und `ReAllocate`.  Wenn der Puffer, der freigegeben wird, der feste Puffer ist, legt die Methode diesen einem gesperrten Puffer der Länge 0 \(null\) fest.  Wenn der Puffer, der freigegeben wurde, mit dem Backup\-Manager zugeordnet wurde, verwendet **CFixedStringMgr** den Backup\-Manager, um es freizugeben.  
  
## Implementierung von CFixedStringMgr::Clone  
 Die Implementierung von **CFixedStringMgr::Clone** gibt immer einen Zeiger auf Backup\-Manager statt **CFixedStringMgr** selbst zurück.  Dies geschieht, da jede Instanz von **CFixedStringMgr** mit einer einzelnen Instanz von `CStringT` nur zugeordnet werden kann.  Alle anderen Instanzen von `CStringT` Versuch, den Manager zu klonen sollten den Backup\-Manager abrufen.  Dies ist die Backup\-Managerunterstützung, da die freigegeben wird.  
  
## Implementierung von CFixedStringMgr::GetNilString  
 Die Implementierung von **CFixedStringMgr::GetNilString** gibt den festen Puffer zurück.  Aufgrund der Einzel\- Entsprechung von **CFixedStringMgr** und von `CStringT`, verwendet eine angegebene Instanz von `CStringT` nie mehr als einen Puffer gleichzeitig.  Daher werden eine Nullzeichenfolge und ein wirklicher Zeichenfolgenpuffer nie gleichzeitig erfordert.  
  
 Sobald der feste Puffer nicht verwendet wird, **CFixedStringMgr** wird sichergestellt, dass es mit einem Länge 0 initialisiert wird.  Dadurch können als die Nullzeichenfolge verwendet werden kann.  Ein weiterer Prämie wird der `nAllocLength`\-Member des feste Puffergröße immer zur vollen Größe des feste Puffergröße festgelegt.  Dies bedeutet, dass die Zeichenfolge `CStringT` wachsen kann, ohne [IAtlStringMgr::Reallocate](../Topic/IAtlStringMgr::Reallocate.md) aufzurufen, auch für die Nullzeichenfolge.  
  
## Anforderungen  
 **Header:** cstringt.h  
  
## Siehe auch  
 [Memory Management with CStringT](../atl-mfc-shared/memory-management-with-cstringt.md)