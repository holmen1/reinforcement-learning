# gridworld

From Microsoft: DAT257x Reinforcement Learning Explained (archived)
https://courses.edx.org/courses/course-v1:Microsoft+DAT257x+3T2019/course/

* random agent

* policy evaluation (MDP)

    V(s) <-  &Sigma; &pi;(a|s) &Sigma; p(s',r|s,a) (r + &gamma; V(s'))

* policy iteration (MDP)

    V(s) <-  &Sigma; p(s',r|s,&pi;(s)) (r + &gamma; V(s'))

    &pi;(s) <- argmax<sub>a</sub> &Sigma; p(s',r|s,a) (r + &gamma; V(s'))

* value iteration (MDP)

    V(s) <- max<sub>a</sub> &Sigma; p(s',r|s,a) (r + &gamma; V(s'))

* sarsa agent

    Q(s,a) <- Q(s,a) + &alpha; (r + &gamma; Q(s',a') - Q(s,a))

* q-learning agent

    Q(s,a) <- Q(s,a) + &alpha; (r + &gamma; max[Q(s') - Q(s,a)]

* linear function approximation

    &theta; <- &theta; + &alpha; (r + &gamma; (max[Q(s') - Q(s,a)])) * f(s,a)

    Q(s,a) = &theta; f(s,a)

* deep q-learning




This library contains modified lab files for Microsoft course DAT257x: Reinforcement Learning Explained

MIT License

Copyright for portions of these lab files are held by Denny Britz as part of https://github.com/dennybritz/reinforcement-learning. All other copyright for these lab files are held by Microsoft."

Copyright (c) 2016 Denny Britz Copyright (c) 2017-present Microsoft

Permission is hereby granted, free of charge, to any person obtaining a copy of this software and associated documentation files (the "Software"), to deal in the Software without restriction, including without limitation the rights to use, copy, modify, merge, publish, distribute, sublicense, and/or sell copies of the Software, and to permit persons to whom the Software is furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in all copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY, FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM, OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE SOFTWARE.

