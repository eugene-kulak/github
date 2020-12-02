# New python source checklist

- [ ] Define the specification for this source connector by modifying `spec.json`.
- [ ] Implement your integration in `source.py` (and creating additional files as necessary).
- [ ] Ensure that all logging done through the `logger` object passed into each method.
- [ ] Update the `sample_files` directory with an example config and catalog (discover output).
- [ ] Create unit tests in `unit_tests` folder.
- [ ] Create integration tests in `integration_tests` folder.
- [ ] Implement each method in `integration_tests/standard_source_test.py` if necessary.
- [ ] `./gradlew :airbyte-integrations:connectors:source-{{dashCase name}}:standardSourceTestPython`
- [ ] Add your source to the source definition registry. In `airbyte-config/init/src/main/resources/seed/source_definitions.yaml` add an entry for the new source. 
Make sure to generate a new _unique_ UUIDv4 for the `sourceDefinitionId` field. You can get one [here](https://www.uuidgenerator.net/). Follow the example of the other entries in the index. Include a unique `name` as well as the `dockerRepository` and `dockerImageTag` for the connectors docker image.
- [ ] Add docs in `docs/integrations/sources/` folder. If API credentials are required to run the integration, please document how they can be obtained.
- [ ] Add link to create docs file to `docs/SUMMARY.md`
- [ ] Update `README.md` to document the usage of your integration.
- [ ] Include a link to the documentation in the `README.md`.
- [ ] From the `airbyte` project root, run `./gradlew build` to make sure your module builds within the rest of the monorepo.
