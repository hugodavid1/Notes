**Exemple :**

```javascript
import { useReducer } from "react";

function reducer(state, action) {
  if (action.hello === "incremented_age") {
    return {
      age: state.age + 1,
    };
  }
  throw Error("Unknown action.");
}

export default function Counter() {
  const [state, dispatch] = useReducer(reducer, { age: 42 });

  return (
    <>
      <button
        onClick={() => {
          dispatch({ hello: "incremented_age" });
        }}
      >
        Increment age
      </button>
      <p>Hello! You are {state.age}.</p>
    </>
  );
}
```

**Explication de la fonction**
Ici : yoyoyo est l'action.
State : Correspond a l'état initial donné en deuxieme paramètre de useReducer
Quand vous cliquez sur le bouton "Increment age", la fonction dispatch est appelée avec l'action { yoyoyo: 'incremented_age' }. Cette action est ensuite traitée par le réducteur. Le réducteur détecte que le type d'action est 'incremented_age' et renvoie un nouvel état avec l'âge augmenté de 1. Le composant est alors re-rendu avec cet état mis à jour, montrant l'âge augmenté.

**Définir le réducteur**

Un réducteur est une fonction qui prend l'état actuel et une action, puis renvoie un nouvel état. Ici, le réducteur vérifie la propriété yoyoyo de l'action. Si elle est égale à 'incremented_age', il renvoie un nouvel état avec l'âge augmenté de 1. Si aucune action reconnue n'est fournie, une erreur est lancée.

**Utiliser useReducer dans le composant:**
Le hook useReducer est appelé avec deux arguments : le réducteur (reducer) et l'état initial ({ age: 42 }). Il renvoie deux valeurs : state (l'état actuel) et dispatch (une fonction pour envoyer des actions au réducteur).

**Rendu du composant:**
Un bouton est rendu avec un gestionnaire d'événements onClick qui, lorsqu'il est cliqué, envoie (ou "dispatche") une action { yoyoyo: 'incremented_age' } au réducteur.
Le paragraphe (<p>) affiche l'âge actuel contenu dans l'état.
