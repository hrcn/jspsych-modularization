## 1. Setup jsPsych Hello World Trial
https://www.jspsych.org/tutorials/hello-world/

## 2. Modify jsPsych.js
Pass type parameter as objects: https://github.com/jspsych/jsPsych/pull/661/

Change `window.jsPsych` to `const jsPsych` at the beginning.

Add `export default jsPsych` at the end.

## 3. Modify Plugin jspsych-html-keyboard-response.js
Add `import jsPsych from '../jspsych.js';` at the top.

Change `jsPsych.plugins["html-keyboard-response"]` to `const htmlKeyboardResponse`

Export it `export default htmlKeyboardResponse` at the end.

## 4. Modify experiment.html
Remove `<script src="jspsych-6.0.5/jspsych.js"></script>` and `<script src="jspsych-6.0.5/plugins/jspsych-html-keyboard-response.js"></script>` warpped in head tag.

Add a attribute `type="module"` in the script tag below: `<script type="module">`

Change the content in the script tag to the following:
```
import jsPsych from './jspsych-6.1.0/jspsych.js';
import htmlKeyboardResponse from './jspsych-6.1.0/plugins/jspsych-html-keyboard-response.js'

var hello_trial = {
    type: htmlKeyboardResponse,
    stimulus: 'Hello world!'
}

jsPsych.init({
    timeline: [hello_trial]
})
```

## 5. Move to AWS S3
