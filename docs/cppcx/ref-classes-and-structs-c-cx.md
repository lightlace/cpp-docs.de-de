---
title: "Verweisklassen und Strukturen (C++/CX) | Microsoft Docs"
ms.custom: ""
ms.date: "01/22/2017"
ms.prod: "windows-client-threshold"
ms.technology: ""
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 3d736b82-0bf0-48cf-bac1-cc9d110b70d1
caps.latest.revision: 42
author: "ghogen"
ms.author: "ghogen"
manager: "ghogen"
caps.handback.revision: 42
---
# Verweisklassen und Strukturen (C++/CX)
[!INCLUDE[cppwrt](../cppcx/includes/cppwrt-md.md)] \([!INCLUDE[cppwrt_short](../cppcx/includes/cppwrt-short-md.md)]\) unterstützt benutzerdefinierte *Verweisklassen* und *Verweisstrukturen* sowie benutzerdefinierte *Wertklassen* und *Wertstrukturen*. Diese Datenstrukturen sind die primären Container, durch die [!INCLUDE[cppwrt_short](../cppcx/includes/cppwrt-short-md.md)] das [!INCLUDE[wrt](../cppcx/includes/wrt-md.md)]\-Typsystem unterstützt. Die Inhalte werden nach bestimmten Regeln an Metadaten ausgegeben und können dadurch zwischen [!INCLUDE[wrt](../cppcx/includes/wrt-md.md)]\-Komponenten und [!INCLUDE[win8_appname_long](../cppcx/includes/win8-appname-long-md.md)]\-Apps, die in C\+\+ oder anderen Sprachen geschrieben sind, ausgetauscht werden.  
  
 Eine Verweisklasse oder Verweisstruktur hat die folgenden wesentlichen Funktionen:  
  
-   Sie muss in einem Namespace und im Umfang des Namespace deklariert werden und darin eine öffentliche oder private Zugreifbarkeit bieten. Nur öffentliche Typen werden an Metadaten ausgegeben. Definitionen der geschachtelten öffentlichen Klasse sind nicht zulässig. Dies schließt geschachtelte öffentliche [enum](../cppcx/enums-c-cx.md)\-Klassen ein. Weitere Informationen finden Sie unter [Namespaces und Typsichtbarkeit](../cppcx/namespaces-and-type-visibility-c-cx.md).  
  
-   Sie kann als Member [!INCLUDE[cppwrt_short](../cppcx/includes/cppwrt-short-md.md)] einschließlich Verweisklassen, Wertklassen, Referenzstrukturen, Wertstrukturen oder auf NULL festlegbare Wertstrukturen enthalten. Sie kann auch skalare Typen wie float64, bool usw. enthalten. Sie kann auch Standard\-C\+\+\-Typen wie `std::vector` oder eine benutzerdefinierte Klasse enthalten, sofern diese nicht öffentlich sind.[!INCLUDE[cppwrt_short](../cppcx/includes/cppwrt-short-md.md)]\-Konstrukte haben möglicherweise `public`, `protected`, `internal`, `private` oder `protected private` Zugreifbarkeit. Alle `public` oder `protected` Member werden an Metadaten ausgegeben. Standard\-C\+\+\-Typen müssen `private`, `internal` oder `protected private` Zugreifbarkeit aufweisen, um zu verhindern, dass sie an Metadaten ausgegeben werden.  
  
-   Sie implementiert möglicherweise eine oder mehrere *Schnittstellenklassen* oder *Schnittstellenstrukturen*.  
  
-   Sie kann jedoch von einer Basisklasse erben, und Basisklassen selbst haben weitere Einschränkungen. Vererbung in öffentlichen Verweisklassenhierarchien ist stärker eingeschränkt als Vererbung in privaten Verweisklassen.  
  
-   Sie kann nicht als generisch deklariert werden. Wenn sie über eine private Zugreifbarkeit verfügt, ist es möglicherweise eine Vorlage.  
  
-   Die Lebensdauer wird durch automatische Verweiszählung verwaltet.  
  
## Deklaration  
 Das folgende Codefragment deklariert die `Person`\-Verweisklasse. Beachten Sie, dass der `std::map`\-C\+\+\-Standardtyp bei den privaten Members verwendet wird und die Schnittstelle [!INCLUDE[wrt](../cppcx/includes/wrt-md.md)]`IMapView` in der öffentlichen Schnittstelle verwendet wird. Beachten Sie außerdem, dass das "^" an die Deklaration von Verweistypen angefügt wird.  
  
 [!code-cpp[cx_classes#03](../snippets/cpp/VS_Snippets_Misc/cx_classes/cpp/class1.h#03)]  
  
## Implementierung  
 Dieses Codebeispiel zeigt eine Implementierung der `Person`\-Verweisklasse.  
  
 [!code-cpp[cx_classes#04](../snippets/cpp/VS_Snippets_Misc/cx_classes/cpp/class1.cpp#04)]  
  
## Verwendung  
 Das nächste Codebeispiel zeigt, wie der Clientcode die `Person`\-Verweisklasse verwendet.  
  
 [!code-cpp[cx_classes#05](../snippets/cpp/VS_Snippets_Misc/cx_classes/cpp/class1.cpp#05)]  
  
 Sie können eine lokale Verweisklassenvariable auch deklarieren, indem Sie Stapelsemantik verwenden. Ein solches Objekt verhält sich wie eine stapelbasierte Variable, auch wenn der Arbeitsspeicher dennoch dynamisch zugeordnet wird. Ein wichtiger Unterschied besteht darin, dass Sie einer mit Stapelsemantik deklarierten Variablen keinen Nachverfolgungsverweis \(%\) zuweisen können. So wird gewährleistet, dass der Verweiszähler auf Null verringert ist, wenn die Funktion beendet wird. In diesem Beispiel wird eine Basisverweisklasse `Uri` dargestellt sowie eine Funktion, die diese Klasse mit Stapelsemantik verwendet:  
  
 [!code-cpp[cx_classes#06](../snippets/cpp/VS_Snippets_Misc/cx_classes/cpp/class1.cpp#06)]  
  
## Speicherverwaltung  
 Sie weisen einer Verweisklasse mit dem Schlüsselwort `ref new` dynamischen Speicher zu.  
  
 [!code-cpp[cx_classes#01](../snippets/cpp/VS_Snippets_Misc/cx_classes/cpp/class1.h#01)]  
  
 Der Handle\-zu\-Objekt\-Operator ^ wird als "Dach" bezeichnet und ist im Grunde ein intelligenter Zeiger in C\+\+. Der Speicher, auf den er zeigt, wird automatisch zerstört, sobald das letzte Dach den Gültigkeitsbereich verlässt oder ausdrücklich auf `nullptr` gesetzt wird.  
  
 Definitionsgemäß verfügt eine Verweisklasse über Verweissemantik. Wenn Sie eine Verweisklassenvariable zuweisen, wird das Handle kopiert, nicht das Objekt selbst. Im nächsten Beispiel zeigen `myClass` und `myClass2` nach der Zuweisung beide auf die gleiche Speicheradresse.  
  
 [!code-cpp[cx_classes#02](../snippets/cpp/VS_Snippets_Misc/cx_classes/cpp/class1.h#02)]  
  
 Beim Instanziieren einer C\+\+\/CX\-Verweisklasse wird ihr Speicher mit 0 \(Null\) initialisiert, bevor der Konstruktor aufgerufen wird. Daher müssen einzelne Member und auch Eigenschaften nicht mit 0 initialisiert werden. Wenn die C\+\+\/CX\-Klasse von einer WRL\-Klasse \(Windows Runtime C\+\+ Library\) abgeleitet ist, wird nur der abgeleitete C\+\+\/CX\-Klassenteil mit 0 initialisiert.  
  
## Mitglieder  
 Eine Verweisklasse kann Funktionsmember enthalten, die `public`, `protected` und `private` sind. Nur `public` und `protected` Member werden in Metadaten ausgegeben. Geschachtelte Klassen und Verweisklassen sind zulässig, können jedoch nicht `public` sein. Öffentliche Felder sind nicht zulässig; öffentliche Datenmember müssen als Eigenschaften deklariert werden. Private oder geschützte interne Datenmember können Felder sein. Standardmäßig ist in einer Verweisklasse die Zugreifbarkeit für alle Member `private`.  
  
 Eine Verweisstruktur ist das Gleiche wie eine Verweisklasse, nur dass auf ihre Member standardmäßig `public` zugegriffen werden kann.  
  
 Eine `public` Verweisklasse oder Verweisstruktur wird in Metadaten ausgegeben, aber um von anderen [!INCLUDE[win8_appname_long](../cppcx/includes/win8-appname-long-md.md)]\-Apps und [!INCLUDE[wrt](../cppcx/includes/wrt-md.md)]\-Komponenten verwendet werden zu können, muss sie über mindestens einen öffentlichen oder geschützten Konstruktor verfügen. Eine öffentliche Verweisklasse mit einem öffentlichen Konstruktor muss außerdem als `sealed` deklariert werden, um weitere Ableitungen über die Anwendungsbinärschnittstelle \(ABI\) zu verhindern.  
  
 Öffentliche Member können nicht als Konstanten deklariert werden, da das [!INCLUDE[wrt](../cppcx/includes/wrt-md.md)]\-Typsystem keine Konstanten unterstützt. Sie können eine statische Eigenschaft verwenden, um einen öffentlichen Datenmember mit einem konstanten Wert zu deklarieren.  
  
 Wenn Sie eine öffentliche Verweisklasse oder Verweisstruktur definieren, ordnet der Compiler die erforderlichen Attribute für die Klasse zu und speichert diese Informationen in der WINMD\-Datei der App. Wenn Sie jedoch eine öffentlich unversiegelte Verweisklasse definieren, müssen Sie das `Windows::Foundation::Metadata::WebHostHidden`\-Attribut manuell zuordnen, um sicherzustellen, dass die Klasse für [!INCLUDE[win8_appname_long](../cppcx/includes/win8-appname-long-md.md)]\-Apps, die in JavaScript geschrieben sind, nicht sichtbar ist.  
  
 Eine Verweisklasse kann über C\+\+\-Standardtypen \(einschließlich `const`\-Typen\) in jedem Member verfügen, das `private`, `internal` oder `protected private` ist.  
  
 Öffentliche Verweisklassen, die über Typparameter verfügen, sind nicht zulässig. Benutzerdefinierte generische Verweisklassen sind nicht zulässig. Eine private, interne oder private geschützte Verweisklasse ist möglicherweise eine Vorlage.  
  
## Destruktoren  
 Das Aufrufen von [!INCLUDE[cppwrt_short](../cppcx/includes/cppwrt-short-md.md)] auf einem öffentlichen Destruktor ruft in `delete` den Destruktor unabhängig vom Verweiszählerwert des Objekts auf. Durch dieses Verhalten können Sie einen Destruktor definieren, der eine benutzerdefinierte Bereinigung von nicht\-RAII\-Ressourcen in einer deterministischen Weise ausführt. Allerdings wird auch in diesem Fall das Objekt selbst nicht aus dem Arbeitsspeicher gelöscht. Der Speicher für das Objekt wird nur freigegeben, wenn der Verweiszähler null erreicht.  
  
 Ist der Destruktor einer Klasse nicht öffentlich, wird er nur aufgerufen, wenn der Verweiszähler null erreicht. Wenn Sie `delete` für ein Objekt aufrufen, das über einen privaten Destruktor verfügt, löst der Compiler die Warnung C4493 aus, die besagt, dass der „Löschausdruck keine Auswirkungen hat, da der Destruktor von \<type name\> keinen 'öffentlichen' Zugriff hat“.  
  
 Verweisklassendestruktoren können nur wie folgt deklariert werden:  
  
-   öffentlich und virtuell \(für versiegelte oder unversiegelte Typen\)  
  
-   geschützt privat und nicht virtuell \(nur für unversiegelte Typen\)  
  
-   privat und nicht virtuell \(nur für versiegelte Typen\)  
  
 Keine andere Kombination von Zugreifbarkeit, Virtualität und Versiegelung ist zulässig.  Wenn Sie nicht explizit einen Destruktor deklarieren, generiert der Compiler einen öffentlichen virtuellen Destruktor, wenn die Basisklasse des Typs oder ein Member einen öffentlichen Destruktor hat. Andernfalls generiert der Compiler einen geschützten, privaten und nicht virtuellen Destruktor für unversiegelte Typen oder einen privaten, nicht virtuellen Destruktor für versiegelte Typen.  
  
 Das Verhalten ist nicht definiert, wenn Sie versuchen, auf die Member einer Klasse zuzugreifen, deren Destruktor bereits ausgeführt wurde. Wahrscheinlich wird das Programm abstürzen. Das Aufrufen von `delete t` für einen Typ, der keinen öffentlichen Destruktor besitzt, hat keine Auswirkungen. Das Aufrufen von `delete this` für einen Typ oder eine Basisklasse, der bzw. die einen bekannten `private`\- oder `protected private`\-Destruktor besitzt, aus der Typhierarchie hat keine Auswirkungen.  
  
 Wenn Sie einen öffentlichen Destruktor deklarieren, generiert der Compiler den Code so, dass die Verweisklasse `Platform::IDisposable` implementiert und der Destruktor die `Dispose`\-Methode implementiert.`Platform::IDisposable` ist die [!INCLUDE[cppwrt_short](../cppcx/includes/cppwrt-short-md.md)]\-Projektion von `Windows::Foundation::IClosable`. Implementieren Sie niemals explizit diese Schnittstellen.  
  
## Vererbung  
 Platform::Object ist die universelle Basisklasse für alle Verweisklassen. Alle Verweisklassen sind implizit konvertierbar in Platform::Object und können [Object::ToString](../cppcx/object-tostring-method-c-cx.md) überschreiben. Das Vererbungsmodell von [!INCLUDE[wrt](../cppcx/includes/wrt-md.md)] ist jedoch nicht als generelles Vererbungsmodell gedacht; in C\+\+\/CX bedeutet dies, dass eine benutzerdefinierte öffentliche Verweisklasse nicht als Basisklasse verwendet werden kann.  
  
 Wenn Sie ein XAML\-Benutzersteuerelement erstellen und das Objekt am Abhängigkeitseigenschaftensystem teilnimmt, können Sie `Windows::UI::Xaml::DependencyObject` als Basisklasse verwenden.  
  
 Nachdem Sie eine unversiegelte Klasse `MyBase` definiert haben, die von `DependencyObject` erbt, können andere öffentliche oder private Verweisklassen in Ihrer Komponente oder App von `MyBase` erben. Vererbung in öffentlichen Verweisklassen sollte nur vorgenommen werden, um Überschreibungen von Methoden, polymorphe Identität und Kapselung zu unterstützen.  
  
 Eine private Basisverweisklasse ist nicht erforderlich, um von einer vorhandenen unversiegelten Klasse abzuleiten. Wenn Sie eine Objekthierarchie benötigen, eine Ihre eigene Programmstruktur zu modellieren oder die Wiederverwendung von Code zu aktivieren, verwenden Sie private oder interne Verweisklassen, oder am besten Standard\-C\+\+\-Klassen. Sie können die Funktionalität der privaten Objekthierarchie durch einen öffentlichen versiegelten Verweisklassenwrapper verfügbar machen.  
  
 Eine Verweisklasse, die in [!INCLUDE[cppwrt_short](../cppcx/includes/cppwrt-short-md.md)] über einen öffentlichen oder geschützten Konstruktor verfügt, muss als versiegelt deklariert werden. Diese Einschränkung bedeutet, dass es keine Möglichkeit für Klassen gibt, die in anderen Sprachen wie C\# oder Visual Basic geschrieben werden, um von Typen erben, die Sie in einer [!INCLUDE[wrt](../cppcx/includes/wrt-md.md)] Komponente deklarieren, die in [!INCLUDE[cppwrt_short](../cppcx/includes/cppwrt-short-md.md)] geschrieben wird.  
  
 Folgende grundlegende Regeln gelten für die Vererbung in [!INCLUDE[cppwrt_short](../cppcx/includes/cppwrt-short-md.md)]:  
  
-   Verweisklassen können direkt von höchstens einer Basisverweisklasse erben, jedoch können eine beliebige Anzahl von Schnittstellen implementieren.  
  
-   Besitzt eine Klasse einen öffentlichen Konstruktor, muss als versiegelt deklariert werden, um eine weitere Ableitung zu verhindern.  
  
-   Sie können öffentliche unversiegelte Basisklassen erstellen, die interne oder geschützte private Konstruktoren besitzen, vorausgesetzt, dass sich die Basisklasse direkt oder indirekt von einer vorhandenen unversiegelten Basisklasse wie `Windows::UI::Xaml::DependencyObject` ableitet. Vererbung von benutzerdefinierten Verweisklassen über WINMD\-Dateien wird nicht unterstützt. Eine Verweisklasse kann jedoch von einer Schnittstelle erben, die in einer anderen WINMD\-Datei definiert ist. Sie können abgeleitete Klassen aus einer benutzerdefinierten Basisverweisklasse nur innerhalb derselben [!INCLUDE[wrt](../cppcx/includes/wrt-md.md)]\-Komponente oder [!INCLUDE[win8_appname_long](../cppcx/includes/win8-appname-long-md.md)]\-App erstellen.  
  
-   Für Verweisklassen wird nur öffentliche Vererbung unterstützt.  
  
     [!code-cpp[cx_classes#08](../snippets/cpp/VS_Snippets_Misc/cx_classes/cpp/class1.h#08)]  
  
 Das folgende Beispiel zeigt, wie eine öffentliche Verweisklasse, die von anderen Verweisklassen abgeleitet wird, in einer Vererbungshierarchie verfügbar gemacht wird.  
  
 [!code-cpp[cx_classes#09](../snippets/cpp/VS_Snippets_Misc/cx_classes/cpp/class1.h#09)]  
  
## Siehe auch  
 [Typsystem](../cppcx/type-system-c-cx.md)   
 [Wertklassen und Strukturen](../cppcx/value-classes-and-structs-c-cx.md)   
 [Sprachreferenz zu Visual C\+\+](../cppcx/visual-c-language-reference-c-cx.md)   
 [Namespaceverweis](../cppcx/namespaces-reference-c-cx.md)