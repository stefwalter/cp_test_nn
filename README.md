# Cockpit Test Neural Network

A neural network that can easily be trained to recognize whether a CI fail is a real fail or happened because of a flaky test.

## How to Run

* Clone this repo && cd to its directory
* Download https://stefw.fedorapeople.org/2017-06-21-2017-07-21-cockpit-test-data.jsonl.gz and https://stefw.fedorapeople.org/2017-06-22-2017-07-22-cockpit-test-data.jsonl.gz
* Install dependencies: `pip3 install --user -r requirements.txt`
* Run it: `python3 -m cp_test_nn ./2017-06-21-2017-07-21-cockpit-test-data.jsonl ./2017-06-22-2017-07-22-cockpit-test-data.jsonl`

## Output

When you run `cp_test_nn`, you'll see bunch of numbers printed - these are progress of creating feature sets from the learning data set (`2017-06-21-2017-07-21-cockpit-test-data.jsonl`) and from validation set (`2017-06-22-2017-07-22-cockpit-test-data.jsonl`). When this is done (this might take couple minutes), the program will output something like:

```
Success rate:  0.9299839657936932
False positives:  0.02244788882950294
False negatives:  0.04756814537680385
```

Your numbers may vary slightly due to random initialization. Generally, success rate on the validation dataset above `0.9` is good - this shows that the approach is sound. The program is still in a very early phase and it should be possible to improve on this.
