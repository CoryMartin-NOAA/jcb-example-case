# jcb-example-case

Simple JCB example that renders a YAML file from an expanded base template inspired by:
`GDASApp/parm/atm/jcb-base.yaml.j2`

## Files

- `example/templates/jcb-base.yaml.j2`: Expanded base Jinja2 YAML template with GDAS-style sections (assimilation, model, obs, LETKF, diagnostics/driver).
- `example/templates/simple_example.yaml.j2`: Algorithm template that includes the base template.
- `example/templates/observer_components.yaml`: Required by JCB renderer (empty for this minimal case).
- `example/dictionary_of_templates.yaml`: Input dictionary consumed by `jcb render`.

## Run

```bash
python3 -m pip install --user jcb
cd example
jcb render dictionary_of_templates.yaml rendered.yaml
```

## Expected output

`example/rendered.yaml` will contain the fully rendered YAML using values from
`dictionary_of_templates.yaml`.

Compare it to `example/rendered_reference.yaml` with `diff` to confirm it worked as intended
