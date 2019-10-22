---
title: Sample Container-Klasse
ms.date: 11/04/2016
helpviewer_keywords:
- container classes [C++]
ms.assetid: 5b1451f2-c708-45da-bbf0-9e42fd687a1a
ms.openlocfilehash: 404e372e65af8b93ae4f6f2827a73ef64336690a
ms.sourcegitcommit: 590e488e51389066a4da4aa06d32d4c362c23393
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/21/2019
ms.locfileid: "72688972"
---
# <a name="sample-container-class"></a>Sample Container-Klasse

> [!NOTE]
> Dieses Thema ist in der Microsoft C++ -Dokumentation als nicht funktionales Beispiel für Container, die C++ in der Standard Bibliothek verwendet werden. Weitere Informationen finden Sie unter [C++-Standardbibliothekscontainer](../standard-library/stl-containers.md).

Beschreibt ein Objekt, das eine Sequenz von Elementen variabler Länge steuert, in der Regel vom Typ `Ty`. Die Folge ist unterschiedlich gespeichert, abhängig vom tatsächlichen Container.

Ein Containerkonstruktor oder eine Memberfunktion finden möglicherweise Anlass, den Konstruktor **Ty**(**const Ty &** ) oder die Funktion **Ty::operator =** (**const Ty &** ) aufzurufen. Wenn solch ein Aufruf eine Ausnahme auslöst, ist das Containerobjekt verpflichtet, seine Integrität beizubehalten, und jede Ausnahme, die es entdeckt, erneut auslösen. Sie können ein Containerobjekt sicher austauschen, zuweisen, löschen oder zerstören, nachdem es eine dieser Ausnahmen auslöst. Im Allgemeinen jedoch können Sie den Zustand der vom Containerobjekt kontrollierten Sequenz andernfalls nicht vorhersagen.

Einige zusätzliche Vorsichtsmaßnahmen:

- Wenn der Ausdruck `~Ty` eine Ausnahme auslöst, ist der resultierende Status des Container Objekts nicht definiert.

- Wenn der Container ein *Zuordnungs Objekt Al*speichert und *Al* eine Ausnahme als Ergebnis eines Aufrufes `al.allocate` auslöst, ist der resultierende Status des Container Objekts nicht definiert.

- Wenn der Container ein Funktionsobjekt *comp* speichert, um zu bestimmen, wie die kontrollierte Sequenz sortiert wird und *comp* eine beliebige Ausnahme auslöst, ist der resultierende Status des Containerobjekts nicht definiert.

Die Containerklassen, die von der C++-Standardbibliothek definiert werden, erfüllen noch weitere Anforderungen, wie in den folgenden Abschnitten beschrieben.

Die [Liste](../standard-library/list-class.md) der Container Klassen Vorlagen bietet deterministisches und nützliches Verhalten, auch wenn die oben beschriebenen Ausnahmen vorhanden sind. Wenn beispielsweise eine Ausnahme während des Einfügens von einem oder mehreren Elementen ausgelöst wird, bleibt der Container unverändert, und die Ausnahme wird erneut ausgelöst.

Für *alle* Containerklassen, die von C++ der Standard Bibliothek definiert werden, wird der Container nicht geändert, wenn eine Ausnahme während Aufrufen der folgenden Member-Funktionen ausgelöst wird: `insert`, `push_back` oder `push_front`, und die Ausnahme wird erneut ausgelöst.

Für *alle* Containerklassen, die von C++ der Standard Bibliothek definiert werden, wird bei Aufrufen der folgenden Member-Funktionen keine Ausnahme ausgelöst: `pop_back` `pop_front`.

Die Memberfunktion [erase](../standard-library/container-class-erase.md) löst eine Ausnahme nur aus, wenn ein Kopiervorgang (Zuweisung oder Copy-Konstruktion) eine Ausnahme auslöst.

Darüber hinaus wird keine Ausnahme ausgelöst, während des Kopiervorgangs eines Iterators, der von einer Memberfunktion zurückgegeben wird.

Die Memberfunktion [swap](../standard-library/container-class-swap.md) macht zusätzliche Zusagen für *alle* Containerklassen, die von der C++-Standardbibliothek definiert werden:

- Die Memberfunktion löst eine Ausnahme nur dann aus, wenn der Container eine Zuweisungsobjekt al speichert und `al` löst beim Kopiervorgang eine Ausnahme aus.

- Verweise, Zeiger und Iteratoren, die getauschte Elemente der gesteuerten Sequenzen anzeigen, bleiben gültig.

Ein Objekt einer Containerklasse, die von der C++-Standardbibliothek definiert wird, reserviert Speicher und gibt ihn für die gesteuerte Sequenz frei, die sie durch ein gespeichertes Objekt vom Typ `Alloc` kontrolliert. Dieser ist gewöhnlich ein Vorlagenparameter. Ein solches zuordnerobjekt muss dieselbe externe Schnittstelle wie ein Objekt der Klasse `allocator<Ty>` haben. Insbesondere muss `Alloc` denselben Typ aufweisen wie `Alloc::rebind<value_type>::other`

Für *alle* Containerklassen, die C++ von der Standard Bibliothek definiert werden, gibt die Member-Funktion `Alloc get_allocator const;` eine Kopie des gespeicherten Zuordnungs Objekts zurück. Beachten Sie, dass das gespeicherte Zuweisungsobjekt *nicht* kopiert wird, wenn das Containerobjekt zugewiesen wird. Alle Konstruktoren initialisieren den in `allocator` gespeicherten Wert, um `Alloc`, wenn der Konstruktor keinen zuordnerparameter enthält.

Entsprechend dem C++-Standard kann eine Container-Klasse, die die C++-Standardbibliothek definiert, folgendes darstellen:

- Alle Objekte der Klasse `Alloc` sind beim Vergleich gleich.

- Der Typ `Alloc::const_pointer` entspricht `const Ty *`.

- Der Typ `Alloc::const_reference` entspricht `const Ty&`.

- Der Typ `Alloc::pointer` entspricht `Ty *`.

- Der Typ `Alloc::reference` entspricht `Ty&`.

In dieser Implementierung treffen Container jedoch nicht solche vereinfachende Annahmen. Daher arbeiten sie ordnungsgemäß mit Zuweisungsobjekten, die ehrgeiziger sind:

- Alle Objekte der `Alloc`-Klasse werden beim Vergleich nicht gleich abschneiden. (Sie können mehrere Speicherpools verwalten.)

- Der Typ `Alloc::const_pointer` muss nicht mit `const Ty *` identisch sein. (Ein const-Zeiger kann eine Klasse sein.)

- Der Typ `Alloc::pointer` muss nicht mit `Ty *` identisch sein. (Ein Zeiger kann eine Klasse sein.)

## <a name="requirements"></a>Anforderungen

**Header**: \<sample container>

## <a name="see-also"></a>Siehe auch

[\<sample container>](../standard-library/sample-container.md)
