---
title: "Vorlagenbasierte Klassen"
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
  - "Arrays [C++], Klassen"
  - "Arrays [C++], Zeiger"
  - "Arrays [C++], Vorlagenbasiert"
  - "CArray-Klasse, Vorlagenbasierte Klassen"
  - "CList-Klasse, Vorlagenbasierte Klassen"
  - "Auflistungsklassen, Vorlagenbasiert"
  - "Auflistungen, Typisierter Zeiger"
  - "CTypedPtrArray-Klasse, Vorlagenbasierte Klassen"
  - "CTypedPtrList-Klasse, Vorlagenbasierte Klassen"
  - "CTypedPtrMap-Klasse, Vorlagenbasierte Klassen"
  - "MFC-Auflistungsklassen, Vorlagenbasiert"
  - "Zeiger, Auflistung typisierter"
  - "simple array-Auflistungsklassen"
  - "simple list-Auflistungsklassen"
  - "Einfache vorlagenbasierte Auflistungen"
  - "Vorlagenbasierte Auflistungsklassen"
  - "Typisierter Zeiger"
  - "Typisierter Zeiger, Auflistungen von"
  - "Typsichere Auflistungen"
ms.assetid: c69fc95b-c8f6-4a99-abed-517c9898ef0c
caps.latest.revision: 10
caps.handback.revision: "6"
ms.author: "mblome"
manager: "ghogen"
---
# Vorlagenbasierte Klassen
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Dieser Artikel beschreibt die typsicheren vorlagenbasierten Auflistungsklassen in MFC 3.0 und höher.  Mithilfe dieser Vorlagen, typsichere Auflistungen ist zu erstellen bequemer und Codierungshilfen gewährleisten Typsicherheit effektiv als die Verwendung von Auflistungsklassen nicht basierend auf Vorlagen bereit.  
  
 MFC definiert zwei Kategorien vorlagenbasierten Auflistungen vor:  
  
-   [Einfaches Array, und Zuordnungsklassen Liste](#_core_using_simple_array.2c_.list.2c_.and_map_templates)  
  
     `CArray`, `CList`, `CMap`  
  
-   [Arrays, Listen und Zuordnungen typisierter Zeiger](#_core_using_typed.2d.pointer_collection_templates)  
  
     `CTypedPtrArray`, `CTypedPtrList`, `CTypedPtrMap`  
  
 Alle einfachen Auflistungsklassen werden von der `CObject`\- Klasse berechnet, daher erben sie die Serialisierung, die dynamische Erstellung und andere Eigenschaften von `CObject`.  Typisierte Zeigerauflistungsklassen benötigen Sie, die Klasse anzugeben, die Sie von abgeleitet \- das eine der nicht auf Vorlagen basierenden Zeigerauflistungen sein, die von MFC, wie `CPtrList` oder `CPtrArray` vordefinierten werden.  Die neue Auflistungsklasse erbt von der angegebenen Basisklasse und den neuen Encapsulated Aufrufen der Memberfunktionen der Klasse verwenden zu den Basisklassenmember, um Typsicherheit erzwingen.  
  
 Weitere Informationen über C\+\+\-Vorlagen, finden Sie unter [Vorlagen](../cpp/templates-cpp.md) in der *C\+\+\-Sprachreferenz*.  
  
##  <a name="_core_using_simple_array.2c_.list.2c_.and_map_templates"></a> Verwenden des einfachen Arrays, der Liste und der Zuordnungs\-Vorlagen  
 Um die einfache Auflistungsvorlagen verwenden müssen Sie wissen, welche Art von Daten Sie in diesen Auflistungen speichern kann und die in den Auflistungsdeklarationen verwenden Parameter.  
  
###  <a name="_core_simple_array_and_list_usage"></a> Einfache Array\- und Listen\-Verwendung  
 Die einfachen Array\- und Listenklassen, [CArray](../mfc/reference/carray-class.md) und [CList](../mfc/reference/clist-class.md), nehmen zwei Parameter: *\<TYP2\>* und `ARG_TYPE`.  Diese Klassen können jeden Datentyp gespeichert, den Sie im *Typparameter* angeben:  
  
-   Grundlegende C\+\+\-Datentypen, wie `int`, `char` und **float**  
  
-   C\+\+\-Strukturen und Klassen  
  
-   Andere Typen, die Sie definieren  
  
 Zur Vereinfachung und Effizienz können Sie den `ARG_TYPE`\-Parameter verwenden, um den Typ von Funktionsargumenten anzugeben.  In der Regel geben Sie `ARG_TYPE` als Verweis auf den Typ an, der im benannten *Typparameter*.  Beispiel:  
  
 [!CODE [NVC_MFCCollections#1](../CodeSnippet/VS_Snippets_Cpp/NVC_MFCCollections#1)]  
  
 Das erste Beispiel deklariert eine Arrayauflistung, `myArray`, die `int`s enthält.  Das zweite Beispiel deklariert eine Listenauflistung, `myList`, die `CPerson`\-Objekte gespeichert werden.  Bestimmte Memberfunktionen Auflistungsklassen erstellen Argumente, deren Typ über den Vorlagenparameter `ARG_TYPE` angegeben wird.  Beispielsweise erfordert die **Hinzufügen**\-Memberfunktion der Klasse `CArray` ein Argument: `ARG_TYPE`  
  
 [!CODE [NVC_MFCCollections#2](../CodeSnippet/VS_Snippets_Cpp/NVC_MFCCollections#2)]  
  
###  <a name="_core_simple_map_usage"></a> Einfache Zuordnungs\-Verwendung  
 Die einfache Assoziationsklasse, [CMap](../mfc/reference/cmap-class.md), nimmt vier Parameter an: *TASTE*, `ARG_KEY`, *WERT* und `ARG_VALUE`.  Wie die Array\- und Listenklassen können die Zuordnungsklassen beliebige Datentypen speichern.  Anders als Arrays und Listen die die Daten verwenden, und sortieren, die sie speichern, verschlüsselt Zuordnungsmitarbeiter und ausgewertet: Sie greifen auf einen Wert zu, der in einer Zuordnung gespeichert wird, indem Sie der zugeordneten Schlüssel des Werts angeben.  Der *SCHLÜSSELparameter* gibt den Datentyp der Schlüssel an, die auf Daten verwendet werden, die in der Zuordnung gespeichert werden.  Wenn der Typ *der TASTE* einer Struktur oder Klasse handelt, ist der Parameter `ARG_KEY` in der Regel ein Verweis auf den Typ, der *in der TASTE* angegeben wird.  Der *Value\-Parameter* gibt den Typ der Elemente an, die in der Zuordnung gespeichert werden.  Wenn der Typ `ARG_VALUE` von einer Struktur oder Klasse handelt, ist der Parameter `ARG_VALUE` in der Regel ein Verweis auf den Typ, der *innerhalb WERT* angegeben wird.  Beispiel:  
  
 [!CODE [NVC_MFCCollections#3](../CodeSnippet/VS_Snippets_Cpp/NVC_MFCCollections#3)]  
  
 Das erste Beispiel speichert `MY_STRUCT`\-Werte, greift über Schlüssel `int` zu und gibt Webserverdurchsatz `MY_STRUCT`\-Elemente nach Verweis zurück.  Das zweite Beispiel speichert `CPerson`\-Werte, greift es durch `CString` Schlüssel und auf Rückgabeverweise auf Webserverdurchsatz Elemente zu.  Dieses Beispiel kann beispielsweise ein einfaches Adressbuch dar, in dem Sie oben Mitwirkende nach Nachnamen aussehen.  
  
 Da der *SCHLÜSSELparameter* vom Typ `CString` ist und der *KEY\_TYPE\-Parameter* vom Typ `LPCSTR` ist, werden die Schlüssel gespeichert, in der Zuordnung als Elemente des Typs `CString` werden in Funktionen wie `SetAt` durch Zeiger vom Typ `LPCSTR`.  Beispiel:  
  
 [!CODE [NVC_MFCCollections#4](../CodeSnippet/VS_Snippets_Cpp/NVC_MFCCollections#4)]  
  
##  <a name="_core_using_typed.2d.pointer_collection_templates"></a> Verwenden der Auflistungs\-Vorlagen des Zeigers typabhängigen  
 Um die Auflistungsvorlagen typabhängigen des Zeigers verwenden müssen Sie wissen, welche Arten von Daten Sie in diesen Auflistungen speichern kann und die in den Auflistungsdeklarationen verwenden Parameter.  
  
###  <a name="_core_typed.2d.pointer_array_and_list_usage"></a> Array des Zeigers und Listen\-Verwendung typabhängigen  
 Die Array\- und Listenklassen des typabhängigen Zeigers, [CTypedPtrArray](../mfc/reference/ctypedptrarray-class.md) und [CTypedPtrList](../mfc/reference/ctypedptrlist-class.md), nehmen zwei Parameter: `BASE_CLASS` und *\<TYP2\>*.  Diese Klassen können jeden Datentyp gespeichert, den Sie im *Typparameter* angeben.  Sie werden von einer der nicht auf Vorlagen basierenden Auflistungsklassen abgeleitet, die Zeiger speichert; Sie geben diese Basisklasse in `BASE_CLASS` an.  Für Arrays verwenden Sie entweder `CObArray` oder `CPtrArray`.  Für Listen verwenden Sie entweder `CObList` oder `CPtrList`.  
  
 Faktisch wenn Sie eine Auflistung anhand deklarieren, sagen Sie `CObList`, die neue Klasse erbt nicht nur die Member der Basisklasse deklariert, jedoch auch einige zusätzliche Memberfunktionen typsichere und Operatoren, die zur Typsicherheit vom Kapseln von Aufrufen der Basisklassenmember bereitstellen.  Diese Kapselungen verwalten alle erforderliche Typkonvertierung.  Beispiel:  
  
 [!CODE [NVC_MFCCollections#5](../CodeSnippet/VS_Snippets_Cpp/NVC_MFCCollections#5)]  
  
 Das erste Beispiel deklariert ein Array des typabhängigen Zeigers, `myArray`, wird von `CObArray` abgeleitet.  Das Array gespeichert und enthält Tipps zu `CPerson`\-Objekten zurück \(wobei `CPerson` eine Klasse ist, die von `CObject` abgeleitet ist\).  Sie können jede `CObArray`\-Memberfunktion aufrufen, oder neue typsichere `GetAt` und die `ElementAt`\-Funktionen aufrufen oder den typsicheren **\[ \]**\-Operator.  
  
 Das zweite Beispiel deklariert eine Liste des typabhängigen Zeigers, `myList`, wird von `CPtrList` abgeleitet.  Die Liste gespeichert und enthält Tipps zu `MY_STRUCT`\-Objekten zurück.  Eine Klasse auf `CPtrList` wird zum Speichern von Zeigern auf Objekte verwendet, die nicht von `CObject` abgeleitet werden.  `CTypedPtrList` verfügt über einige typsichere Memberfunktionen: `GetHead`, `GetTail`, `RemoveHead`, `RemoveTail`, `GetNext`, `GetPrev` und `GetAt`.  
  
###  <a name="_core_typed.2d.pointer_map_usage"></a> Zuordnungs\-Verwendung des Zeigers typabhängigen  
 Die Assoziationsklasse typabhängigen des Zeigers, [CTypedPtrMap](../mfc/reference/ctypedptrmap-class.md), nimmt drei Parameter: `BASE_CLASS`, *TASTE* und *WERT*.  Der `BASE_CLASS`\-Parameter gibt die Klasse an, von der die neue Klasse abgeleitet werden: `CMapPtrToWord`, `CMapPtrToPtr`, `CMapStringToPtr`, `CMapWordToPtr`, `CMapStringToOb`, z. B.  *TASTE* ist analog, `CMap`*VERSCHLÜSSELN TO* : Sie gibt den Typ des Schlüssels an, die bei Suchvorgängen verwendet wird.  *WERT* ist analog, `CMap`*BEWERTEN TO* : Sie gibt den Typ des Objekts gespeichert in der Zuordnung an.  Beispiel:  
  
 [!CODE [NVC_MFCCollections#6](../CodeSnippet/VS_Snippets_Cpp/NVC_MFCCollections#6)]  
  
 Das erste Beispiel ist eine Zuordnung auf Grundlage **CMapPtrToPt** r \- Es verwendet Schlüssel `CString`, die den Zeiger `MY_STRUCT` zugeordnet werden.  Sie können einen gespeicherten Zeiger nachsehen, indem Sie eine typsichere `Lookup`\-Memberfunktion aufrufen.  Sie können den **\[ \]**\-Operator verwenden, um einen gespeicherten Zeiger gesucht wird und ihn hinzuzufügen, wenn sie nicht gefunden wird.  Außerdem können Sie die Zuordnung mit typsicheren `GetNextAssoc`\-Funktion durchlaufen.  Sie können andere Memberfunktionen der Klasse auch `CMapPtrToPtr` aufrufen.  
  
 Das zweite Beispiel ist eine Zuordnung auf Grundlage b **CMapStringToO**\- Es verwendet die Zeichenfolgentasten, die an gespeicherten Zeigern zu `CMyObject`\-Objekten zugeordnet sind.  Sie können dieselben typsicheren Member verwenden, die im vorherigen Absatz beschrieben werden, oder Sie können Member der Klasse `CMapStringToOb`.  
  
> [!NOTE]
>  Wenn Sie **Klasse** oder `struct` einem Typ für den *Value\-Parameter* angeben, keinen Zeiger oder Verweis auf den Typ, müssen die Klasse oder Struktur einen Kopierkonstruktor aufweisen.  
  
 Weitere Informationen finden Sie unter [Wie Sie eine typsichere Auflistung macht](../mfc/how-to-make-a-type-safe-collection.md).  
  
## Siehe auch  
 [Auflistungen](../mfc/collections.md)