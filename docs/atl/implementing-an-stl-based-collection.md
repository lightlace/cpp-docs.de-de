---
title: "Implementing an STL-Based Collection | Microsoft Docs"
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
  - "ICollectionOnSTLImpl interface"
ms.assetid: 6d49f819-1957-4813-b074-3f12c494d8ca
caps.latest.revision: 12
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 7
---
# Implementing an STL-Based Collection
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

ATL stellt die `ICollectionOnSTLImpl`\-Schnittstelle, um es Ihnen ermöglicht, Auflistungsschnittstellen der Standardvorlagenbibliothek \(STL\) auf den Objekten \- basierte schnell zu implementieren.  Um zu verstehen wie diese Klasse funktioniert, arbeiten Sie durch ein einfaches Beispiel \(unten\) dieses mithilfe dieser Klasse angestrebte Automatisierung zu implementieren Clients einer schreibgeschützte Auflistung.  
  
 Der Beispielcode ist von [ATLCollections\-Beispiel](../top/visual-cpp-samples.md).  
  
 Um diese Prozedur abzuschließen, werden Sie:  
  
-   [Generieren Sie ein neues einfaches Objekt](#vccongenerating_an_object).  
  
-   [Bearbeiten Sie die IDL\-Datei](#vcconedit_the_idl) für die generierte Schnittstelle.  
  
-   [Erstellen Sie fünf Typdefinitionen](#vcconstorage_and_exposure_typedefs), das beschreibt, wie die Auflistungselemente gespeichert werden und wie sie von Clients über COM\-Schnittstellen verfügbar gemacht werden.  
  
-   [Erstellen Sie zwei Typdefinitionen für Kopierrichtlinienklassen](#vcconcopy_classes).  
  
-   [Erstellen Sie Typdefinitionen für die Enumerator\- und Auflistungsimplementierungen](#vcconenumeration_and_collection).  
  
-   [Bearbeiten Sie den vom Assistenten generierten C\+\+\-Code, um die Auflistung Typedef zu verwenden](#vcconedit_the_generated_code).  
  
-   [Fügen Sie Code hinzu, um die Auflistung aufzufüllen](#vcconpopulate_the_collection).  
  
##  <a name="vccongenerating_an_object"></a> Generieren eines neuen einfachen Objekts  
 Erstellen Sie ein neues Projekt und sicherstellen, dass das Attributfeld mit Anwendungseinstellungen gelöscht wird.  Verwenden Sie das ATL hinzufügen Klassendialogfeld und einfachen Objekt\-Assistenten hinzufügen, um ein einfaches Objekt zu generieren, das `Words` aufgerufen wird.  Überprüfen Sie, ob eine duale Schnittstelle, die `IWords` aufgerufen wird, generiert wird.  Objekte der generierten Klasse werden verwendet, um eine Auflistung Wörter \(das heißt, Zeichenfolgen\) darzustellen.  
  
##  <a name="vcconedit_the_idl"></a> Bearbeiten der IDL\-Datei  
 Jetzt öffnen Sie die IDL\-Datei und fügen Sie die drei Eigenschaften hinzu, die erforderlich sind, `IWords` zu eine schreibgeschützte Auflistungsschnittstelle auszuführen, wie unten dargestellt:  
  
 [!CODE [NVC_ATL_COM#24](../CodeSnippet/VS_Snippets_Cpp/NVC_ATL_COM#24)]  
  
 Dies ist das Standardformular für eine schreibgeschützte Auflistungsschnittstelle, die mit Automatisierungsclients im Auge entworfen wurde.  Die nummerierten Kommentare in dieser Schnittstellendefinition entsprechen den Kommentaren folgendermaßen:  
  
1.  Auflistungsschnittstellen sind normalerweise Dual, da Automatisierungsclients auf die `_NewEnum`\-Eigenschaft über **IDispatch::Invoke** zugreift.  Allerdings können Automatisierungsclients auf die übrigen Methoden zum vtable zugreifen, daher sind duale Schnittstellen in Dispatchschnittstellen vorzuziehen.  
  
2.  Wenn eine duale Schnittstelle oder eine Dispatchschnittstelle nicht zur Laufzeit \(das heißt, stellen zusätzliche Methoden oder Eigenschaften nicht über **IDispatch::Invoke**\) bereit, erweitert werden, sollten Sie das **nonextensible**\-Attribut auf die Definition anwenden.  Mit diesem Attribut können Automatisierungsclients, um die Überprüfung des vollständigen Code zur Kompilierzeit auszuführen.  In diesem Fall sollte die Schnittstelle nicht erweitert werden.  
  
3.  Das richtige DISPID ist wichtig, wenn Sie Automatisierungsclients in der Lage sein sollen, diese Eigenschaft zu verwenden.  \(Beachten Sie, dass es nur einen Unterstrich in **DISPID\_NEWENUM** gibt\).  
  
4.  Sie können einen beliebigen Wert als den DISPID der **Item**\-Eigenschaft bereitstellen.  verwendet jedoch **Item** in der Regel **DISPID\_VALUE**, um es die Standardeigenschaft aus der Auflistung zu machen.  Dadurch können Automatisierungsclients, um die Eigenschaft zuzugreifen, ohne sie explizit zu benennen.  
  
5.  Der Datentyp, der für den Rückgabewert der **Item**\-Eigenschaft verwendet wird, ist der Typ des Elements, das in der Auflistung gespeichert wird, insoweit COM\-Clients.  Die Schnittstelle gibt Zeichenfolgen zurück, sollten Sie den Zeichenfolgentyp des standardmäßigen COM, `BSTR` verwenden.  Sie können die Daten in einem anderen Format intern speichern, da Sie weiter unten unter.  
  
6.  Der Wert, der für das DISPID der **Count**\-Eigenschaft verwendet wird, ist vollständig beliebig.  Es gibt keinen Standardwert DISPID für diese Eigenschaft.  
  
##  <a name="vcconstorage_and_exposure_typedefs"></a> Erstellen von Typdefinitionen für Speicher und verursachte  
 Sobald die Auflistungsschnittstelle definiert ist, müssen Sie entscheiden, wie die Daten gespeichert werden und wie die Daten über den Enumerator verfügbar gemacht werden.  
  
 Antworten auf diese Fragen können in Form von einigen Typdefinitionen bereitgestellt werden, die Sie im oberen Bereich der Headerdatei für die neu erstellte Klasse hinzufügen können:  
  
 [!CODE [NVC_ATL_COM#25](../CodeSnippet/VS_Snippets_Cpp/NVC_ATL_COM#25)]  
  
 In diesem Fall speichern Sie die Daten als **std::vector** of **std::string**s.  **std::vector** ist eine STL\-Containerklasse, die wie ein verwaltetes Array verhält.  **std::string** ist die Standard\-Zeichenfolgenklasse der C\+\+\-Bibliothek.  Diese Klassen ist es einfach, mit einer Auflistung von Zeichenfolgen zu arbeiten.  
  
 Da Visual Basic\-Unterstützung zum Erfolg dieser Schnittstelle wichtig ist, muss der Enumerator, der von der `_NewEnum`\-Eigenschaft zurückgegeben wird, die **IEnumVARIANT**\-Schnittstelle unterstützen.  Dies ist die einzige Enumeratorschnittstelle, die von Visual Basic erkannt wird.  
  
##  <a name="vcconcopy_classes"></a> Erstellen von Typdefinitionen für Kopierrichtlinienklassen  
 Die Typdefinitionen, die Sie bis jetzt erstellt haben, stellen alle Informationen Sie weitere Typdefinitionen für die Kopienklassen erstellen müssen, die durch den Enumerator und die Auflistung verwendet werden:  
  
 [!CODE [NVC_ATL_COM#26](../CodeSnippet/VS_Snippets_Cpp/NVC_ATL_COM#26)]  
  
 In diesem Beispiel können Sie die benutzerdefinierte `GenericCopy`\-Klasse verwenden, die in VCUE\_Copy.h und VCUE\_CopyString.h vom [ATLCollections](../top/visual-cpp-samples.md)\-Beispiel definiert ist.  Sie können diese Klasse in anderem Code verwenden, jedoch müssen Sie möglicherweise weitere Spezialisierungen von `GenericCopy` definieren, um die Datentypen zu unterstützen, die in eigenen Auflistungen verwendet werden.  Weitere Informationen finden Sie unter [ATL\-Kopierrichtlinien\-Klassen](../atl/atl-copy-policy-classes.md).  
  
##  <a name="vcconenumeration_and_collection"></a> Erstellen von Typdefinitionen für Enumeration und Auflistung  
 Jetzt sind alle Vorlagenparameter, die erforderlich sind, die `CComEnumOnSTL` und `ICollectionOnSTLImpl`\-Klassen für diese Situation zu spezialisieren, in Form von Typdefinitionen bereitgestellt wurde.  Um die Verwendung der Spezialisierungen zu vereinfachen, erstellen Sie zwei weitere Typdefinitionen wie unten dargestellt:  
  
 [!CODE [NVC_ATL_COM#27](../CodeSnippet/VS_Snippets_Cpp/NVC_ATL_COM#27)]  
  
 Jetzt ist `CollectionType` ein Synonym für eine Spezialisierung von `ICollectionOnSTLImpl`, die die `IWords`\-Schnittstelle implementiert, die zuvor definiert ist und stellt einen Enumerator, der **IEnumVARIANT** unterstützt.  
  
##  <a name="vcconedit_the_generated_code"></a> Bearbeiten des vom Assistenten generierten Codes  
 Jetzt müssen Sie `CWords` aus der Schnittstellenimplementierung abgeleitet sind, die von `CollectionType`\-Typedef statt `IWords`, wie unten dargestellt wird:  
  
 [!CODE [NVC_ATL_COM#28](../CodeSnippet/VS_Snippets_Cpp/NVC_ATL_COM#28)]  
  
##  <a name="vcconpopulate_the_collection"></a> Hinzufügen von Code, um die Auflistung aufzufüllen  
 Lediglich, bleibt, besteht darin, den Vektor mit Daten aufzufüllen.  In diesem einfachen Beispiel können Sie mehrere Wörter der Auflistung im Konstruktor für die Klasse hinzufügen:  
  
 [!CODE [NVC_ATL_COM#29](../CodeSnippet/VS_Snippets_Cpp/NVC_ATL_COM#29)]  
  
 Jetzt können Sie den Code mit dem Client Ihrer Wahl testen.  
  
## Siehe auch  
 [Auflistungen und Enumerationen](../atl/atl-collections-and-enumerators.md)   
 [ATLCollections\-Beispiel](../top/visual-cpp-samples.md)   
 [ATL Copy Policy Classes](../atl/atl-copy-policy-classes.md)