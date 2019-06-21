# awesome-jest-articles

[![Awesome](https://cdn.rawgit.com/sindresorhus/awesome/d7305f38d29fed78fa85652e3a63e154dd8e8829/media/badge.svg)](https://github.com/ChickenKyiv/awesome-jest-articles) [![Made With Love](https://img.shields.io/badge/Made%20With-Love-orange.svg)](https://github.com/ChickenKyiv/awesome-jest-articles)
![astronaut](https://raw.githubusercontent.com/GroceriStar/creative/master/website-illustrations/astronaut.svg?sanitize=true)

still unformatted, soo

1.  https://medium.freecodecamp.org/how-to-set-up-jest-enzyme-like-a-boss-8455a2bc6d56



https://medium.com/groceristar/things-that-should-read-and-use-javascript-intern-at-groceristar-april-18-collection-bd6541e9ae28



https://medium.freecodecamp.org/components-testing-in-react-what-and-how-to-test-with-jest-and-enzyme-7c1cace99de5




x. JEST FORMS




https://github.com/xogeny/ts-jest-sample

https://github.com/lnmunhoz/redux-jest-example/blob/master/src/__tests__/actions.js


---


ーmockー 

https://medium.com/@ansertechgeek/migrating-from-mocha-to-jest-in-nodejs-app-8afdfa4032d1



---



https://hackernoon.com/javascript-testing-and-debugging-tools-ee81374c01aa
https://medium.com/welldone-software/an-overview-of-javascript-testing-in-2018-f68950900bc3


---

---

#### jest config
https://jestjs.io/docs/en/configuration.html 

https://jest-bot.github.io/jest/docs/configuration.html 

https://stackoverflow.com/questions/30027494/how-to-write-a-jest-configuration-file

https://basarat.gitbooks.io/typescript/docs/testing/jest.html


#### jest react+enzyme

ENZYME GUIDE
https://airbnb.io/enzyme/docs/guides/jest.html


https://airbnb.io/enzyme/

install + adapter

https://codesandbox.io/s/zlo6qky294
https://codesandbox.io/s/v0yykvk640




https://github.com/ferrannp/enzyme-example-jest
https://github.com/ferrannp/enzyme-example-jest/blob/master/src/__tests__/MyComponent-test.js



https://stackoverflow.com/questions/47754777/jest-how-to-test-for-object-keys-and-properties

#### Default first test
```
import React from 'react';
import ReactDOM from 'react-dom';
import Enzyme, {shallow, configure } from 'enzyme';
import Adapter from 'enzyme-adapter-react-16';
import { Calendar } from '../component/Calendar/Calendar';

Enzyme.configure({ adapter: new Adapter() });

describe('<Calendar />', () => {
    it('renders without crashing', () => {
        const div = document.createElement('div');
        ReactDOM.render(<Calendar />, div);
    });
});
```



https://github.com/airbnb/enzyme/issues/1636#issuecomment-385427899

https://airbnb.io/enzyme/docs/api/ShallowWrapper/setContext.html



ENZYME GUIDE
https://airbnb.io/enzyme/docs/guides/jest.html


https://airbnb.io/enzyme/

install + adapter


https://hackernoon.com/testing-react-components-with-jest-and-enzyme-41d592c174f



https://medium.com/netscape/testing-a-react-redux-app-using-jest-and-enzyme-b349324803a9


1) Shallow rendering renders only component itself without its children. So if you change something in a child component it won’t change shallow output of your component. Or a bug, introduced to a child component, won’t break your component’s test. It also doesn’t require DOM.


1) Shallow Rendering(shallow method)

Shallow rendering is useful to constrain yourself to testing a component as a unit, and to ensure that your tests aren't indirectly asserting on behavior of child components.


Docs for methods that can be combined with shallow
https://airbnb.io/enzyme/docs/api/shallow.html#shallowwrapper-api


2) Full Rendering(mount method)
Full DOM rendering is ideal for use cases where you have components that may interact with DOM APIs or need to test components that are wrapped in higher order components.

3) Static Rendering(render method)
enzyme's render function is used to render react components to static HTML and analyze the resulting HTML structure.


---

if you need installation guide
https://airbnb.io/enzyme/#installation

```import Adapter from 'enzyme-adapter-react-16';

Enzyme.configure({ adapter: new Adapter() });
```
you should also install and adapter - that help enzyme to work with your project.
we're using latest react, so we actually don't care a lot about it. 
adapters table are part of installation guide.


THIS IS AN OLD VERSION> WE CAN USE ONLY LOGIC OF DESCRIBE AND THAT IT.

https://github.com/securingsincity/react-jest-example/blob/master/app/__tests__/button.js
https://github.com/securingsincity/react-jest-example/blob/master/app/__tests__/container.js
https://github.com/securingsincity/react-jest-example/blob/master/app/__tests__/task.js#L19

https://github.com/securingsincity/react-jest-example/blob/master/app/__tests__/taskmanager.js#L17
ーー-

https://github.com/reactstrap/reactstrap/blob/master/src/__tests__/Alert.spec.js

https://github.com/reactstrap/reactstrap/blob/master/src/__tests__/Form.spec.js


Selectors
 pretty similar to jquery/css selectors (so if you familar with this syntax - it'll be easy for you)
https://airbnb.io/enzyme/docs/api/selector.html



enzyme — JS testing utility developed by Airbnb to make it easier to assert React Components.



Why Enzyme
* Convenient utilities to work with shallow rendering, static rendered markup or DOMrendering.
* jQuery-like API to find elements, read props, etc.



https://devhints.io/enzyme

---

SHALLOW
1 

```
describe('<MyComponent />', () => {
////
// render an HTML tag inside
it('renders a header', () => {
const wrapper = shallow(<MyComponent />);
expect(wrapper.contains(<h1>My Component</h1>)).toBe(true);
});

///
// count child elements/components inside
it('renders three <Foo /> components', () => {
const wrapper = shallow(<MyComponent />);
expect(wrapper.find(Foo).length).toBe(3);
});

///
// simulate events like click
wrap.find('input').simulate('click')
wrap.find('button.submit').simulate('click')


// find class or other props
it('should render with "form-inline" class', () => {
const wrapper = shallow(<Form inline>Yo!</Form>);

expect(wrapper.hasClass('form-inline')).toBe(true);
});

it('should render additional classes', () => {
const wrapper = shallow(<Form className="other">Yo!</Form>);

expect(wrapper.hasClass('other')).toBe(true);
});

//
// find children
it('renders children when passed in', () => {
const wrapper = shallow((
<MyComponent>
<div className="unique" />
</MyComponent>
));
expect(wrapper.contains(<div className="unique" />)).to.equal(true);
});
```


* Calendar 

* Showcase

* https://github.com/ChickenKyiv/recipe-box/blob/master/src/components/EditRecipeModal/EditRecipeModal.js

Note, if you want to know more about events you should start from this: https://reactjs.org/docs/handling-events.html



---

https://blog.bitsrc.io/how-to-test-react-components-using-jest-and-enzyme-fab851a43875

https://medium.com/netscape/testing-a-react-redux-app-using-jest-and-enzyme-b349324803a9
this is more about differences and not a lot about enzyme basic stuff.



---

#### jest enzyme mount

https://airbnb.io/enzyme/docs/api/mount.html

Full DOM rendering is ideal for use cases where you have components that may interact with DOM APIs or need to test components that are wrapped in higher order components.

```
const wrapper = mount(
            <div>
                <Dummy id="find-me"/>
            </div>,
        );


wrapper.debug()

```
```
it('calls componentDidMount', () => {
    sinon.spy(Foo.prototype, 'componentDidMount');
    const wrapper = mount(<Foo />);
    expect(Foo.prototype.componentDidMount).to.have.property('callCount', 1);
  });

  it('allows us to set props', () => {
    const wrapper = mount(<Foo bar="baz" />);
    expect(wrapper.props().bar).to.equal('baz');
    wrapper.setProps({ bar: 'foo' });
    expect(wrapper.props().bar).to.equal('foo');
  });


wrap.setProps({ name: 'Moe' })
wrap.setState({ show: true })

expect(wrap.props('name')).toEqual('Moe')
expect(wrap.state('show')).toEqual(true)

expect('name' in wrap.props()).toEqual(true)
expect('show' in wrap.state()).toEqual(true)

```

Mount is more deeper method.
what you can do with it - everything that you do at shallow ,but also you can have a parent-child collaboration.

check if compoentns have method didMount or other methods

allow us to set properties

debug - will help you if you'll stuck at something and don't know how exaclty your compoentn is rendered.

Debug is a good thing. because sometimes you can be confused



- https://github.com/airbnb/enzyme/issues/1253

- https://www.fullstackreact.com/30-days-of-react/day-25/

- https://devhints.io/enzyme

- http://blog.sapegin.me/all/react-jest


https://github.com/reactstrap/reactstrap/blob/master/src/__tests__/Form.spec.js

- https://hackernoon.com/testing-react-components-with-jest-and-enzyme-41d592c174f

- https://blog.bitsrc.io/how-to-test-react-components-using-jest-and-enzyme-fab851a43875

- https://bambielli.com/til/2018-03-04-directly-test-react-component-methods/

- https://github.com/airbnb/enzyme/blob/master/docs/api/mount.md



---

#### just articles

- https://hackernoon.com/api-testing-with-jest-d1ab74005c0a

- https://medium.com/@ryandrewjohnson/unit-testing-components-using-reacts-new-context-api-4a5219f4b3fe

- https://medium.com/@wyattsweet/testing-react-components-using-the-new-context-api-a1c553edc2fa











#### THIS IS MY KING
https://flaviocopes.com/jest/








https://medium.com/quick-code/how-to-integrate-eslint-prettier-in-react-6efbd206d5c4




https://trello.com/c/lkbZOZsS/11-homepage-components-testing




- https://github.com/wesbos/React-Context

- https://www.codementor.io/community/topic/jest
- https://www.sitepoint.com/test-react-components-jest/

- https://facebook.github.io/jest/docs/en/getting-started.html
- https://facebook.github.io/jest/docs/en/tutorial-react.html
- https://hackernoon.com/api-testing-with-jest-d1ab74005c0a




- https://jestjs.io/docs/en/mock-functions
- https://stackoverflow.com/questions/50737711/react-s-new-context-api-with-enzyme

- https://www.google.com.ua/search?q=jest+react+native&oq=jest+react+native&aqs=chrome..69i57j0l5.5975j0j1&sourceid=chrome&ie=UTF-8



- https://github.com/kentcdodds/testing-workshop

- https://github.com/smooth-code/jest-puppeteer

- https://github.com/kentcdodds/react-testing-library/issues/152

- https://github.com/kentcdodds/react-testing-library-course

- https://github.com/christianalfoni/formsy-react/issues/495 



https://github.com/vlucas/frisby

https://www.google.com.ua/search?q=jest+examples+github&oq=jest+examples+github&aqs=chrome..69i57.3591j0j4&sourceid=chrome&ie=UTF-8

https://www.google.com.ua/search?q=jest+complex+examples&oq=jest+complex+examples&aqs=chrome..69i57.5896j0j1&sourceid=chrome&ie=UTF-8

https://github.com/lund0n/test-doubles




#### react native


https://deltice.github.io/jest/docs/en/tutorial-react-native.html

https://airbnb.io/enzyme/docs/guides/react-native.html


#### snaphots

- https://medium.com/@stipsan/testing-with-jest-15-awesome-tips-and-tricks-42150ec4c262


- https://semaphoreci.com/community/tutorials/snapshot-testing-react-components-with-jest

- https://medium.com/@michaelsholty/using-jest-snapshots-in-a-marionette-application-even-with-handlebars-f5c152525006


#### forms

https://github.com/kentcdodds/react-testing-library-course/blob/master/src/__tests__/tdd-02-state.js

https://github.com/kentcdodds/react-testing-library-course/blob/master/src/__tests__/tdd-01-markup.js

https://github.com/kentcdodds/react-testing-library-course/blob/master/src/post-editor-02-state.js




#### jest grapql

GRAPHQL TESTING WITH JEST 

Testing a GraphQL Server using Jest
https://medium.com/entria/testing-a-graphql-server-using-jest-4e00d0e4980e

GraphQL Jest snapshot testing
https://itnext.io/graphql-jest-snapshot-testing-7f7345ee2be

Parallel Testing a graphQL server with Jest
https://itnext.io/parallel-testing-a-graphql-server-with-jest-44e206f3e7d2

Extensive GraphQL testing
https://hackernoon.com/extensive-graphql-testing-57e8760f1c25

GraphQL guides(i think it not work)
https://www.graphql.com/guides/

TypeScript
- https://www.youtube.com/watch?v=dE0OTdEIXx4

- https://www.youtube.com/watch?v=j9NZ6SlJfp0

- https://www.youtube.com/watch?v=XyqV-kE08Yo

GraphQL repository with Jest
https://github.com/BinPar/jest-gql

Tests
https://gist.github.com/nzaghini/e038ff05c60bc2c5435f8331f890cea4
Jest Transform GraphQL
https://github.com/remind101/jest-transform-graphql

Testing GraphQL container components with React Apollo and Jest 
https://blog.usejournal.com/testing-graphql-container-components-with-react-apollo-and-jest-9706a00b4aeb

- https://stackoverflow.com/questions/50501324/testing-graphql-resolvers-with-jest
- https://www.apollographql.com/docs/graphql-tools/mocking.html
- https://www.robinwieruch.de/react-apollo-client-testing/
- https://dev.to/iwilsonq/learn-to-architect-and-test-graphql-servers-by-observing-spectrum-5din
- https://frontendmasters.com/courses/advanced-graphql/integration-test-with-jest/
- https://focus.parabol.co/unit-test-your-db-with-graphql-and-jest-d88722b4551e
- https://www.npmjs.com/package/jest-transform-graphql


#### mock
https://jestjs.io/docs/en/mock-functions

https://github.com/lund0n/test-doubles


https://medium.com/@rickhanlonii/understanding-jest-mocks-f0046c68e53c



mock
https://medium.com/@stipsan/testing-with-jest-15-awesome-tips-and-tricks-42150ec4c262



https://github.com/reactstrap/reactstrap/blob/master/src/__tests__/Alert.spec.js

https://github.com/sapegin/jest-cheat-sheet#mocks

Examples: https://github.com/facebook/jest/blob/master/examples/

#### Nodejs endpoints
- https://blog.campvanilla.com/jest-expressjs-and-the-eaddrinuse-error-bac39356c33a

---

- https://github.com/jest-community/jest-extended
- https://github.com/airbnb/jest-wrap
