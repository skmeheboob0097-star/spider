syntax = "proto3";
package worldmonitor.intelligence.v1;

message CustomGeoJsonFeature {
  string id = 1;
  string geometry_type = 2; // e.g., "Polygon", "Point"
  string coordinates_json = 3; // Stringified GeoJSON coordinate array
  map<string, string> properties = 4; // Metadata for map tooltips
}

message GetCustomLayerResponse {
  repeated CustomGeoJsonFeature features = 1;
}

service CustomLayerService {
  rpc GetFeatures (GetCustomLayerRequest) returns (GetCustomLayerResponse);
}
