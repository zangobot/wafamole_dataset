# WAF-A-MoLE Dataset

This is the dataset used in ["WAF-A-MoLE: Evading Web Application Firewalls through Adversarial Machine Learning"](https://dl.acm.org/doi/pdf/10.1145/3341105.3373962).

## How to cite us
If you use this dataset, please cite us:

```bibtex
@article{demetrio2020waf,
  title={WAF-A-MoLE: Evading Web Application Firewalls through Adversarial Machine Learning},
  author={Demetrio, Luca and Valenza, Andrea and Costa, Gabriele and Lagorio, Giovanni},
  journal={Proceedings of the 35th Annual ACM Symposium on Applied Computing},
  year={2020}
}

```

## Using this dataset

Since GitHub does not allow files larger than 25MB, we divided them in chunks.
In our paper, we used the full `attacks.sql` and `sane.sql` files.
You can use each chunk by itself, but this feature is untested.

**WARNING**: each payload might contain `\n`, *do not* split this file by `\n` or you will get incomplete queries. The correct way of getting single samples is to use `sqlparse`.

```python
>>> import sqlparse

>>> # Split a string containing two SQL statements:
>>> attacks = open('attacks.sql', 'r')
>>> statements = sqlparse.split(attacks)
>>> statements
['select * from foo;', 'select * from bar;', ... ]
```
