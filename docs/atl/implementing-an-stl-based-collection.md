---
title: Implementieren einer C++-Standard Library-basierte Auflistung | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords: ICollectionOnSTLImpl interface
ms.assetid: 6d49f819-1957-4813-b074-3f12c494d8ca
caps.latest.revision: "12"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: f5b80b55361a8f7bfa195b08d02feb94af0874bc
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="implementing-a-c-standard-library-based-collection"></a>Implementieren einer C++-Standard-Library-basierte-Auflistung
ATL stellt die `ICollectionOnSTLImpl` Schnittstelle, um C++-Standardbibliothek basierende Auflistungsschnittstellen schnell auf Ihre Objekte implementieren können. Um zu verstehen, wie diese Klasse funktioniert, arbeiten Sie über ein einfaches Beispiel (siehe unten), die diese Klasse verwendet, um eine schreibgeschützte Auflistung, die Automatisierungsclients Vorbeugung zu implementieren.  
  
 Der Beispielcode stammt aus dem [-Beispiel](../visual-cpp-samples.md).  
  
 Um dieses Verfahren auszuführen, führen Sie folgende Aktionen ausführen:  
  
-   [Generieren Sie ein neues Objekt für die einfache](#vccongenerating_an_object).  
  
-   [Bearbeiten Sie die IDL-Datei](#vcconedit_the_idl) für die generierten-Schnittstelle.  
  
-   [Erstellen Sie fünf Typdefinitionen](#vcconstorage_and_exposure_typedefs) beschreiben, wie die Elemente der Auflistung gespeichert werden und wie sie für Clients über COM-Schnittstellen verfügbar gemacht werden.  
  
-   [Erstellen Sie zwei Typdefinitionen für die kopiesicherung richtlinienklassen](#vcconcopy_classes).  
  
-   [Erstellen Sie die Typdefinitionen für Implementierungen der Enumerator und der Auflistung](#vcconenumeration_and_collection).  
  
-   [Bearbeiten Sie die vom Assistenten generierten C++-Code um die Auflistung Typedef verwenden](#vcconedit_the_generated_code).  
  
-   [Fügen Sie Code zum Auffüllen der Auflistung](#vcconpopulate_the_collection).  
  
##  <a name="vccongenerating_an_object"></a>Generieren ein neues einfaches Objekt  
 Erstellen Sie ein neues Projekt, um sicherzustellen, dass das Feld "Attribute" unter "Einstellungen" Anwendung deaktiviert ist. Mithilfe des Dialogfelds ATL-Klasse hinzufügen, und fügen Assistent für einfache Objekte zum Generieren eines einfachen Objekts aufgerufen `Words`. Stellen Sie sicher, dass eine duale Schnittstelle aufgerufen `IWords` generiert wird. Objekte der generierten Klasse werden zum Darstellen einer Auflistung von Wörtern (d. h. Zeichenfolgen) verwendet werden.  
  
##  <a name="vcconedit_the_idl"></a>Bearbeiten die IDL-Datei  
 Öffnen Sie jetzt die IDL-Datei und fügen Sie die drei Eigenschaften, die zum Aktivieren `IWords` in eine schreibgeschützte Auflistung-Schnittstelle, wie unten dargestellt:  
  
 [!code-cpp[NVC_ATL_COM#24](../atl/codesnippet/cpp/implementing-an-stl-based-collection_1.idl)]  
  
 Dies ist das Standardformat für eine schreibgeschützte Auflistung-Schnittstelle, die mit Automatisierungsclients Bedenken konzipiert. Die nummerierten Kommentare in dieser Schnittstellendefinition entsprechen die folgenden Kommentare:  
  
1.  Collection-Schnittstellen sind in der Regel zwei, da Automatisierungsclients greift auf die `_NewEnum` Eigenschaft über **IDispatch:: Invoke**. Allerdings können Automatisierungsclients die restlichen Methoden über die Vtable zugreifen, damit duale Schnittstellen, Dispatchschnittstellen vorzuziehen sind.  
  
2.  Wenn eine duale Schnittstelle oder Disp-Schnittstelle wird nicht zur Laufzeit erweitert (d. h. Sie wird nicht bereitstellen, zusätzlichen Methoden oder Eigenschaften über **IDispatch:: Invoke**), sollten Sie übernehmen die **nonextensible** -Attribut auf die Definition. Mit diesem Attribut können Automatisierungsclients um vollständige codeüberprüfung, zum Zeitpunkt der Kompilierung auszuführen. In diesem Fall sollte die Schnittstelle nicht erweitert werden.  
  
3.  Die korrekte DISPID ist wichtig, wenn der Benutzeroberflächenautomatisierungs-Clients können diese Eigenschaft verwendet werden soll. (Beachten Sie, dass nur ein Unterstrich im **DISPID_NEWENUM**.)  
  
4.  Sie können einen beliebigen Wert angeben, wie die DISPID eines der **Element** Eigenschaft. Allerdings **Element** verwendet in der Regel **DISPID_VALUE** zu erleichtern die Standardeigenschaft der Auflistung. Dadurch können Benutzeroberflächenautomatisierungs-Clients für die Eigenschaft zu verweisen, ohne Sie explizit zu benennen.  
  
5.  Der Datentyp für den Rückgabewert verwendet die **Element** Eigenschaft ist der Typ des Elements in der Auflistung gespeichert wird, soweit com-Clients betroffen sind. Die Schnittstelle gibt Zeichenfolgen zurück, damit Sie den standard-COM-String-Datentyp verwenden, sollten `BSTR`. Sie können die Daten intern in einem anderen Format speichern, wie Sie in Kürze sehen.  
  
6.  Der Wert für die DISPID eines der **Anzahl** Eigenschaft ist willkürlich. Es ist keine standard DISPID für diese Eigenschaft.  
  
##  <a name="vcconstorage_and_exposure_typedefs"></a>Erstellen von Typdefinitionen für die Speicherung und Offenlegung  
 Nachdem die Auflistungsschnittstelle definiert ist, müssen Sie entscheiden, wie die Daten gespeichert werden sollen und wie die Daten über den Enumerator verfügbar gemacht werden.  
  
 Die Antworten auf diese Fragen können in Form einer Reihe von Typdefinitionen, bereitgestellt werden, den Sie am oberen Rand der Headerdatei für die neu erstellte Klasse hinzufügen können:  
  
 [!code-cpp[NVC_ATL_COM#25](../atl/codesnippet/cpp/implementing-an-stl-based-collection_2.h)]  
  
 In diesem Fall speichert die Daten als ein **Std:: vector** von **Std:: String**s. **Std:: vector** ist eine Containerklasse für C++-Standardbibliothek, die sich wie ein verwaltetes Array verhält. **Std:: String** ist der C++-Standardbibliothek String-Klasse. Diese Klassen vereinfachen das Arbeiten mit einer Auflistung von Zeichenfolgen.  
  
 Da Visual Basic-Unterstützung für den Erfolg dieser Schnittstelle wichtiger ist, der Enumerator zurückgegebenes der `_NewEnum` Eigenschaft unterstützen muss die **IEnumVARIANT** Schnittstelle. Dies ist die einzige Enumeratorschnittstelle, die vom Visual Basic.  
  
##  <a name="vcconcopy_classes"></a>Erstellen von Typdefinitionen für Kopierrichtlinienklassen  
 Die Typdefinitionen Ihnen bisher erstellte Geben Sie alle Informationen, die Sie benötigen weitere Typdefinitionen für die Kopierklassen erstellen, die vom Enumerator und der Auflistung verwendet werden:  
  
 [!code-cpp[NVC_ATL_COM#26](../atl/codesnippet/cpp/implementing-an-stl-based-collection_3.h)]  
  
 In diesem Beispiel können Sie die benutzerdefinierte `GenericCopy` in VCUE_Copy.h und VCUE_CopyString.h aus Klasse definiert die [ATLCollections](../visual-cpp-samples.md) Beispiel. Verwenden Sie diese Klasse in einem anderen Code, jedoch müssen Sie möglicherweise genauer definieren, die spezialisierungen von `GenericCopy` zur Unterstützung von Datentypen in Eigene Sammlungen verwendet. Weitere Informationen finden Sie unter [ATL Kopierrichtlinienklassen](../atl/atl-copy-policy-classes.md).  
  
##  <a name="vcconenumeration_and_collection"></a>Erstellen von Typdefinitionen für Enumeration und Auflistung  
 Jetzt alle Vorlagenparameter zum spezialisieren der `CComEnumOnSTL` und `ICollectionOnSTLImpl` Klassen in dieser Situation in Form von Typdefinitionen zur Verfügung. Um die Verwendung von die spezialisierungen zu vereinfachen, erstellen Sie zwei weitere Typdefinitionen, wie unten dargestellt:  
  
 [!code-cpp[NVC_ATL_COM#27](../atl/codesnippet/cpp/implementing-an-stl-based-collection_4.h)]  
  
 Jetzt `CollectionType` ist ein Synonym für eine Spezialisierung der `ICollectionOnSTLImpl` , implementiert die `IWords` Schnittstelle zuvor definierten und stellt einen Enumerator bereit, unterstützt **IEnumVARIANT**.  
  
##  <a name="vcconedit_the_generated_code"></a>Bearbeiten den vom Assistenten generierter Code  
 Nachdem Sie ableiten müssen `CWords` aus der Implementierung durch dargestellt der `CollectionType` Typedef statt `IWords`, wie unten dargestellt:  
  
 [!code-cpp[NVC_ATL_COM#28](../atl/codesnippet/cpp/implementing-an-stl-based-collection_5.h)]  
  
##  <a name="vcconpopulate_the_collection"></a>Hinzufügen von Code zum Auffüllen der-Auflistung  
 Das einzige, die verbleibt, wird den Vektor mit Daten aufgefüllt. In diesem einfachen Beispiel können Sie einige Wörter auf die Auflistung im Konstruktor für die Klasse hinzufügen:  
  
 [!code-cpp[NVC_ATL_COM#29](../atl/codesnippet/cpp/implementing-an-stl-based-collection_6.h)]  
  
 Jetzt können Sie den Code mit dem Client Ihrer Wahl testen.  
  
## <a name="see-also"></a>Siehe auch  
 [Auflistungen und-Enumerationen](../atl/atl-collections-and-enumerators.md)   
 [-Beispiel](../visual-cpp-samples.md)   
 [ATL-Kopierrichtlinienklasse](../atl/atl-copy-policy-classes.md)

